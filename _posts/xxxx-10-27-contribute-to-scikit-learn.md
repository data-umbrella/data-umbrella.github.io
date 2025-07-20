---
layout: post
title:  Contributing to scikit-learn
description: In this example, learn how to set up your virtual environment and submit a pull request to scikit-learn.
date:   2021-10-27 15:01:35 +0300
image:  '/images/blogs/xxx.png'
tags:   [opensource, scikitlearn, python]
---

Author:  [Reshama Shaikh](https://reshamas.github.io)  

## Python Set-Up
I use 
```bash
conda -V
```
```bash
conda 4.10.3
```

```bash
which python
```
```bash
/Users/reshamashaikh/miniforge3/bin/
```

```bash
python -V
```
```bash
Python 3.9.7
```

## About My Operating System
These instructions work for MacOS Catalina.  

You may need to update the steps depending on whether you are using Linux or Windows.

## Cleaning up My System Python
I had another version of Anaconda installed.  I ran the below command.
```bash
anaconda-clean
```

I also checked my directories and removed any anaconda installations.  I also removed any reference to conda environment paths in my bash profile file.  

## Installing Anaconda
I used [conda miniforge](https://github.com/conda-forge/miniforge) Python installation.

```bash
wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-x86_64.sh
```

#### Updating `profile` file
A profile file is used by bash to load user configurations.  

I use [`Zsh`](https://ohmyz.sh/), and this step updates my `zsh_profile` file by telling my system which path to use for conda installation:  
```bash
zsh Miniforge3-MacOSX-x86_64.sh
```

Note, you will need to edit the commands if you are using another profile type.  

## Fork & Clone the Repo


## Using Virtual Environments
Detailed instructions on building from source are in the scikit-learn [Contributing Guide].

"Build from source" means using the code that is on the GitHub repo to contribute to, as it is the "live version."  It has code updates since the last release was made to pip and conda.  

```bash
# clonar repositorio de sklearn
cd scikit-learn

# create the virtual environment
conda create --name sklearndev

# activate the virtual environment
conda activate sklearndev

# install the needed packages
conda install numpy scipy matplotlib pytest sphinx cython ipykernel jupyter pytest-cov flake8 mypy

conda install -c conda-forge sphinx-gallery pre-commit

# install packages needed that are not in conda, but are available via pip
pip install black==21.6b0

# this installs scikit-learn dev mode
pip install --no-build-isolation --editable .

# allows us to run code style checks before each commit
pre-commit install
```

### To work on this NumPy docs validation pull request ?? really needed?

```bash
pip install cython pytest pytest-cov flake8 mypy black==21.6b0
pip install --no-build-isolation --editable .
```

## Setting up other virtual environments
It's a good practie to create a virtual environment for each project you are working on.

```
conda a
 2309  conda create --name talks
 2310  conda activate talks
 2311  conda install jupyter notebook
 2312  jupyter notebook
 2313  which jupyter
 2314  conda install jupyterhub
 2315  conda install jupyterlab
 2316  jupyterlab
 2317  jupyter lab
 2318  pwd
 2319  conda activate talks
 2320  conda install pandas
 2321  conda install plotly
 2322  conda install watermark

# see package versions
pip freeze
```

## Tracking Impact
If this article is helpful and you submit a PR to scikit-learn, please include the following tags in your pull request so we can track the impact:
```text
#DataUmbrella @reshamas
```
