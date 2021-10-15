---
layout: post
title:  Pair Programming with Visual Studio Code Live Share
description: Introduction to the Visual Studio Code extension Live Share which allows you to edit snippets collaboratively.
date:   2021-09-23 15:01:35 +0300
image:  '/images/vsc/pair_programming_cover_image.jpg'
tags:   [opensource, python, vscode]
---

Author:  [Juan Martin Loyola](https://jmloyola.github.io/)

Pair programming is an amazing experience. On one hand, you and your coding partner can accomplish much more than you would be working separately. On the other hand, both can learn new things about the language or framework you are working on from one another. But, mainly, solving problems and coding challenges with somebody else is a lot of fun :).


This document aims to introduce the Visual Studio Code extension [Live Share](https://visualstudio.microsoft.com/services/live-share/), which allows you to collaborate with coding partners in real-time.

## Live Share
Live Share is an extension from [Visual Studio Code](https://code.visualstudio.com/) that allows you to collaboratively edit and debug with others in real-time. It allows you to instantly share your current project, edit snippets of code at the same time or follow someone’s cursor while they program.
These are extremely helpful when you are pair-programming using the driver-navigator technique [^1]. While the driver codes, the navigator can observe, check other sources, or suggest changes.

[^1]: If you want to read more about pair-programming and the different techniques you can use, visit this [link](https://medium.com/@weblab_tech/pair-programming-guide-a76ca43ff389).

## Installation
To install Live Share follow these steps:
1. If needed, install Visual Studio Code. We used version 1.60.2 for this tutorial. For other versions, some steps might be different.
2. Install the Python extensions and select the Python interpreter you want to use.
3. Download and install the Live Share extension for Visual Studio Code. Use the extensions tab in Visual Studio Code (Ctrl+Shift+X) and search for Live Share. You will see three extensions: Live Share, Live Share Audio, and Live Share Extension Pack. Only the first one, Live Share, is necessary. The last one contains the two previous extensions.
4. Wait for the extension to finish downloading and then reload VS Code when prompted.
5. Wait for Visual Studio Live Share to finish installing dependencies (you’ll see progress updates in the status bar).
6. Once complete, you’ll see Live Share appear in your status bar and the activity bar.
    {:refdef: style="text-align: center;"}
    ![Live Share Status Bar](/images/vsc/live_share_status_bar.png){:width="150px"}
    ![Live Share Status Bar](/images/vsc/live_share_activity_bar.png){:width="25px"}
    {: refdef}
7. [Optional] Sign in with GitHub to use Live Share. For that go to the “Account” tab in the left panel. In case you don’t sign in, you can only join sessions anonymously, and I think you will not be able to start a session. In some web browsers, GitHub authentication can fail. Try a different web browser.

## How to use it
In what follows, we are going to assume two people [^2] are pair-programming, where one takes the role of the driver (in the screenshots represented using the dark theme) and the other is the navigator (in the screenshots represented using the light theme).

[^2]: Note that you can work with more than two people using the Live Share extension.

1. **[driver]** To begin a Live Share session you can:
    - Make sure that the folder you want to work in is open.
    - Click on “Live Share” on the status bar, or
    - Click on the Live Share icon in the activity bar and then click on “Share”.
    {:refdef: style="text-align: center;"}
    ![Create Session](/images/vsc/create_session.png){:width="400px"}
    {: refdef}
2. **[driver]** You should see a notification with a message saying your collaboration session is starting.
3. **[driver]** Once the session starts, a link will be copied to your clipboard. Send it to the person you want to collaborate with.
4. **[navigator]** To join the collaboration session, go to the Live Share icon in the activity bar and click “Join”. If you have the link in your clipboard, when you click on “Join” it will automatically join the session. Otherwise, you will have to paste the link in the panel that appears in the center of the screen. Now you should wait for the driver to accept you into the session.
    {:refdef: style="text-align: center;"}
    ![Join Session](/images/vsc/join_session.png){:width="400px"}
    {: refdef}
5. **[driver]** Accept the navigator into the collaboration session.
    {:refdef: style="text-align: center;"}
    ![Accept Session](/images/vsc/accept_session.png){:width="300px"}
    {: refdef}
6. You will now see the Live Session details showing the other participants. You can now start working collaboratively :).
    {:refdef: style="text-align: center;"}
    ![Working Session](/images/vsc/working_session.png){:width="200px"}
    {: refdef}
7. You can start following each other while you code. This is extremely useful when discussing code over a voice channel.
    - To begin following your partner click on their name.
        {:refdef: style="text-align: center;"}
        ![Following Partner](/images/vsc/following_you.png){:width="600px"}
        {: refdef}
    - To make your partner follow you click on “Focus Participants”.
        {:refdef: style="text-align: center;"}
        ![Follow Me](/images/vsc/follow_me.png){:width="200px"}
        {: refdef}
8. You can chat with the rest of the participants using the “Session chat” on the Live Share tab.
9. **[driver]** You can also share a terminal using the Live Share tab (in read-only or read/write mode). Once allowed, you can remove it. Once activated in read/write mode, all the participants will share the same terminal, so be careful not to step on each other's commands.
10. To end the session you have to click on “Stop Collaboration Session”.
    {:refdef: style="text-align: center;"}
    ![End Session](/images/vsc/end_session.png){:width="200px"}
    {: refdef}

## Notes
While working collaboratively on Live Share, all the changes will appear as if they had been made by the host of the session (the driver). Thus, remember to appropriately indicate that the work was done as a team in the [commit message](https://docs.github.com/es/github/committing-changes-to-your-project/creating-and-editing-commits/creating-a-commit-with-multiple-authors) :D.

## More information
For more information or if you encounter a problem while installing or using Live Share, visit these pages:
- [Visual Studio Code Marketplace: Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)
- [Documentation: Visual Studio Live Share](https://docs.microsoft.com/en-us/visualstudio/liveshare/)
