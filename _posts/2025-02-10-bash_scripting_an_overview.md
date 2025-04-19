---
layout: post
title:  "Getting Started with Bash Scripting"
description: Linux
date:   2025-03-29 15:00:00 +0530
image:  '/images/blogs/rebecca_Intro_to_bash_scripting_square.png'
tags:   [linux, bash, opensource]
author: Sangam Swadi K
---

Posted by: [Sangam Swadi K](https://www.linkedin.com/in/sangam-swadi-k/)

This post explores the fundamentals of Bash scripting, focusing on how it's used in data science workflows and how to write more effective scripts. It builds upon the core concepts presented in the Data Umbrella webinar, [ Intro to Bash Scripting](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=189s)

## Intro to Bash Scripting: by Rebecca BurWei

<p>
<iframe src="https://www.youtube.com/embed/1pQ527fGhVQ" loading="lazy" frameborder="0" allowfullscreen></iframe>
</p>

## Resources
- Repo: [https://github.com/rebecca-burwei/intro-to-bash-scripting/](https://github.com/rebecca-burwei/intro-to-bash-scripting/)
- Slides: [https://docs.google.com/presentation/d/1X9pOOEFOIK2oI26VvuNKRBC8psIM8HnGqOZ6fOUF8jM/](https://docs.google.com/presentation/d/1X9pOOEFOIK2oI26VvuNKRBC8psIM8HnGqOZ6fOUF8jM/)
- Bash file examples: [https://github.com/rebecca-burwei/intro-to-bash-scripting/tree/main/bin](https://github.com/rebecca-burwei/intro-to-bash-scripting/tree/main/bin)

## Section Timestamps of Video 

- [00:00](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=0s) Data Umbrella Introduction
- [04:05](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=245s) Rebecca begins presentation
- [05:24](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=324s) Agenda
- [05:39](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=339s) What is bash? A brief history of shells
- [06:56](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=416s) What is bash used for?
- [07:58](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=476s) Scripting basics + resources
- [09:36](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=576s) What does this code do? Analyzing an ETL script
- [11:20](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=680s) (three min. of quiet time begins)
- [14:24](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=864s) Begin code walkthrough
- [15:33](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=933s) Deeper dive on curl and ssconvert
- [18:33](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1113s) Continuing code walkthrough
- [20:16](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1216s) Quick summary
- [20:45](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1245s) Making the code into a script
- [22:45](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1365s) Making the script executable
- [24:17](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1457s) Running the script
- [25:52](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1552s) Turning code into a script - best practices
- [26:01](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1561s) Ways to customize your bash environment
- [26:54](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1614s) Customize bash environment - .bashrc example
- [28:36](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1716s) Song break + interactive chat time
- [33:06](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1986s) Returning from break, reviewing chat
- [34:27](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=2067s) Improving the script - error handling + demo
- [41:04](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=2464s) Error handling - more resources
- [41:24](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=2484s) Improving the script - logging + demo
- [46:15](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=2775s) Improving the script - options + demo
- [50:00](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=3000s) (two min of quiet time begins)
- [52:05](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=3125s) Continuing options demo
- [54:16](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=3256s) Summary + mentorship/collaboration
- [55:07](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=3307s) Q&A - ssconvert/gnumeric, GNU, esac

## What is Bash and Why Use It?

Bash, short for "Born Again Shell," is a command-line interpreter that allows users to interact with Unix-like operating systems (e.g., macOS, Linux). [ A fun fact, Bash stands for Born Again Shell, which is just a play on the name of that first shell.](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=387s) It's a powerful tool for tasks like file management, process control, and job automation.  While not typically used for core data analysis tasks like model building or statistical analysis, Bash is invaluable for setting up environments, managing files, and automating repetitive tasks.

## A Basic ETL Script in Bash

Let's examine a simple script that performs an Extract, Transform, Load (ETL) process. This script downloads an Excel file, converts it to CSVs, extracts a specific column, and then cleans up the downloaded files.

```bash
#!/bin/bash
# Title: Process Data
# Date: 2024-03-14
# Author: Rebecca BurWei
# Version: 1.0
# Description: Download data, convert to CSV, extract column, and clean up.
# Options: None

URL="http://www.econ.yale.edu/~shiller/data/ie_data.xls"
echo "Downloading data from $URL"  # Print a message indicating the download source.
curl -O stock_data.xls "$URL" # Download the file using curl. The -O option saves it with its original name.
ssconvert -S stock_data.xls stock_data.csv # Convert the Excel file to multiple CSV files (one per sheet).
cut -d, -f10 stock_data.csv.4 | head  # Extract the 10th column (using comma as delimiter) and display the first few lines.
rm stock_data* # Remove all downloaded and created files (using wildcard *).
```

The script begins with a shebang (`#!/bin/bash`), which specifies the interpreter. [ The first comment is a special one. It's a special type of comment called a shebang or a hashbang.](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1304s) It then defines a variable `URL` containing the download link. The `echo` command prints a message to the console. The `curl` command downloads the file, and `ssconvert` converts it into multiple CSV files. [ So I think this will not work if you don't have SS convert installed.](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1016s) The `cut` command extracts the 10th column, using a comma (`,`) as the delimiter, and `head` displays the first few lines of the output. Finally, `rm` removes the downloaded and created files.
<figure>
<a href="https://www.youtube.com/watch?v=1pQ527fGhVQ&t=505.82s" target="_blank"><img src="/images/blogs/rebecca_linux_image_at_505.82.png" alt=" So here's some code." width="450"/></a>
  <figcaption>Figure 1: Resources</figcaption>
</figure>

To make this code executable as a script, save it in a file (e.g., `process.sh`), and use the `chmod` command to grant execute permissions:

```bash
chmod u+x process.sh
```
[ so I'm going to give the owner execute permissions so that the script can be run by using `chmod`.](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=119s)

You can run the script using either `source process.sh` (runs in the current shell) or `./process.sh` (runs in a subshell). [ If you type just the name on then the current shell will create a subshell and run your script in just that subshell.](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=178s) The latter is generally preferred for cleaner execution.

```bash
source process.sh

Bash provides several files to [customize your environment](https://youtu.be/1pQ527fGhVQ?si=lGkFFhyLODqmZLEP&t=1559).  Key files include:

1.  **`.bash_profile`**:  Executed upon login (opening a new terminal). There's a bash profile and this will run on login.
2.  **`.bashrc`**: Executed when a new subshell is started.
3.  **`.bash_logout`**: Executed upon logout, useful for cleanup tasks.

These files can be used to set aliases, define environment variables, export variables, and configure shell behavior.

## Enhancing the Script: Error Handling

By default, Bash continues execution even if a command encounters an error. This behavior can be modified. One approach is to use `set -e` (or `set -o errexit`), which causes the script to exit immediately upon encountering an error. [ You can set air exit and this will make the bash stop when it runs into an error.](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=796s)

A more robust approach is to use `trap`.  `trap` allows you to define custom actions to be taken when specific signals are received.  A common use case is to handle the `ERR` signal, which is triggered when a command exits with a non-zero status (indicating an error).

Here's how to implement error handling with `trap` in the script:

```bash
#!/bin/bash
# ... (previous comments) ...

handle_error() {
  echo "Error on line $1 with exit status $?"
  exit 1
}

trap 'handle_error $LINENO' ERR

URL="invalid_url" # Introduce an error for demonstration.
echo "Attempting to download data from $URL"
curl -O "$URL"
ssconvert -S stock_data.xlsx stock_data.csv
cut -d, -f10 stock_data.csv.0 | head
rm stock_data*

```
<figure>
<a href="https://www.youtube.com/watch?v=1pQ527fGhVQ&t=895.0s" target="_blank"><img src="/images/blogs/rebecca_linux_image_at_895.00.png" alt=" OK, so in this file we have the comments at the top as before." width="450"/></a>
<figcaption>Figure 2: Code explanation</figcaption>
</figure>

In this modified script, `handle_error` is a function that prints an error message including the line number (`$1`, passed from `$LINENO`) and the exit status (`$?`). [ $1 refers to the first argument or the first positional parameter and $? refers to the status code or the exit status of the last command that was run.](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1071s) The `trap` command associates this function with the `ERR` signal. Setting `URL` to an invalid value demonstrates the error handling in action.

## Enhancing the Script: Logging

Instead of printing output directly to the terminal, it's often beneficial to redirect output and errors to files. This is called logging.

You can achieve this using redirection operators:

*   `>` redirects standard output (stdout) to a file.
*   `>>` redirects standard error (stderr) to a file.

Here's how to modify the script execution to implement logging:

```bash
./process.sh > output.txt 2> errors.txt
```

[ So anything that would have gone to the terminal on standard out, send that to this file instead.](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1236s)

This command runs `process.sh` and redirects its standard output to `output.txt` and its standard error to `errors.txt`.

To encapsulate the logging within a separate script, you can use a wrapper script like this. Here is the `logger.sh` script:

```bash
#!/bin/bash
# ... (comments) ...
# Options:
#   $1: Path to the script to be logged.

"$1" > "${1}_output.txt" 2> "${1}_errors.txt"
```
<figure>
  <a href="https://www.youtube.com/watch?v=1pQ527fGhVQ&t=1298.28s" target="_blank"><img src="/images/blogs/rebecca_linux_image_at_1298.28.png" alt=" OK, so I've already prepared an example of logging in a script called logger." width="450"/></a>
  <figcaption>Figure 3: Making the code into script</figcaption>
</figure>
This `logger.sh` script takes the path to another script (passed as the first positional parameter, `$1`) and executes it, redirecting output and errors to files with appropriate names.

## Enhancing the Script: Adding Options

Using positional parameters (`$1`, `$2`, etc.) can be fragile because the order matters. Options (e.g., `-f`, `-d`) provide a more robust and user-friendly way to configure script behavior. The `getopts` built-in command helps parse options.

Here's a modified version of the script that accepts an `-f` option to specify the columns to extract:

```bash
#!/bin/bash
# ... (previous comments) ...
# Options:
#   -f <fields>: Comma-separated list of fields to extract.

while getopts "f:" opt; do
  case $opt in
    f)
      fields="$OPTARG"
      ;;
    \?)
      echo "Usage: $0 [-f <fields>]"
      exit 1
      ;;
  esac
done

URL="http://www.econ.yale.edu/~shiller/data/ie_data.xls"
echo "Downloading data from $URL"
curl -O "$URL"
ssconvert -S stock_data.xlsx stock_data.csv
cut -d, -f"$fields" stock_data.csv.0 | head
rm stock_data*
```

This version uses `getopts "f:" opt` to parse the `-f` option. [ In line 16, that string f colon tells you about the valid options.](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=537s) The colon after `f` indicates that it requires an argument.  The `case` statement handles the option: if `-f` is provided, its value (accessed via `$OPTARG`) is stored in the `fields` variable. [ So fields would be 10 or 10,1.](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=564s) If an invalid option is provided, a usage message is printed, and the script exits. The `cut` command now uses `-f"$fields"` to extract the specified columns. The `esac` closes out the case statement. [ When you create a lot of these control structures, like you type case to start it, and then ESAC, which is case backwards, to end the case statement, to tell Bash, you know, case part is done.](https://www.youtube.com/watch?v=1pQ527fGhVQ&t=982s)

These examples show how to build upon a simple Bash script to add functionality, improve robustness, and make it more user-friendly.


## About the Speaker: Rebecca BurWei

Rebecca BurWei is a Staff Data Scientist at Mozilla. She has a patent in computer vision and a PhD in mathematics. She learned to code in open-source communities, and is passionate about developing the technical leadership of others.

### Connect with the Speaker
- GitHub: [rebecca-burwei](https://github.com/rebecca-burwei)
- LinkedIn: [Rebecca BurWei](https://www.linkedin.com/in/rebecca-burwei/)

