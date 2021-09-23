---
layout: post
title:  Pair Programming with Visual Studio Code Live Share
description: Juan Martin Loyola - Pair Programming with Visual Studio Code Live Share
date:   2021-09-23 15:01:35 +0300
image:  '/images/vsc/join_session.png'
tags:   [opensource, python, vscode]
---

Author:  [Juan Martin Loyola](https://jmloyola.github.io/)

Pair programming is an amazing experience. On one hand, you and your coding partner can accomplish much more than you would working separately. On the other hand, both can learn new things about the language or framework you are working on from one another. But, mainly, solving problems and coding challenges with somebody else is a lot of fun :).

This document aims to introduce the Visual Studio Code extension [Live Share](https://visualstudio.microsoft.com/services/live-share/), which allows you to collaborate with coding buddies in real time.

## Live Share
Live Share is an extension from [Visual Studio Code](https://code.visualstudio.com/) that allows you to collaboratively edit and debug with others in real time. It allows you to instantly share your current project, edit snippets of code at the same time or follow someone's cursor while they program.
These are extremely helpful when you are pair-programming using the driver-navigator technique (If you want to read more about pair-programming and the different techniques you can use, visit this [link](https://medium.com/@weblab_tech/pair-programming-guide-a76ca43ff389)). While the driver codes, the navigator can observe, check other sources or suggest changes.

## Installation
To install Live Share follow these steps:
1. If needed, install Visual Studio Code.
2. Download and install the Visual Studio Live Share extension for Visual Studio Code. Use the extensions tab in Visual Studio Code (Ctrl+Shift+X) and search for Live Share.
3. Wait for the extension to finish downloading and then reload VS Code when prompted.
4. Wait for Visual Studio Live Share to finish installing dependencies (you'll see progress updates in the status bar).
5. Once complete, you'll see Live Share appear in your status bar and in the activity bar.
![Live Share Status Bar](/images/vsc/live_share_status_bar.png)
![Live Share Status Bar](/images/vsc/live_share_activity_bar.png)

## How to use it
In what follows, we are going to assume two people are pair-programming, where one takes the role of the driver (in the screenshots represented using the dark theme) and the other is the navigator (in the screenshots represented using the light theme).

1. **[driver]** To begin a Live Share session you can:
	- Click on “Live Share” on the status bar, or
	- Click on the Live Share icon in the activity bar and then click on “Share”. ![Create Session](/images/vsc/create_session.png)
2. **[driver]** You should see a notification with a message saying your collaboration session is starting.
3. **[driver]** Once the session starts, a link will be copied to your clipboard. Send it to the person you want to collaborate with.
4. **[navigator]** To join the collaboration session, go to the Live Share icon in the activity bar and click “Join”. A pop up is going to ask for the link the driver sent you, paste it there. Now you should wait for the driver to accept you into the session. ![Join Session](/images/vsc/join_session.png)
5. **[driver]** Accept the navigator into the collaboration session. ![Accept Session](/images/vsc/accept_session.png)
6. You will now see the Live Session details showing the other participants. You can now start working collaboratively :) ![Working Session](/images/vsc/working_session.png)
7. You can start following each other while you code. This is extremely useful when discussing code over a voice channel.
	- To begin following your partner click on their name. ![Following Partner](/images/vsc/following_you.png)
	- To make your partner follow you click on “Focus Participants”. ![Follow Me](/images/vsc/follow_me.png)
8. To end the session you have to click on “Stop Collaboration Session”. ![End Session](/images/vsc/end_session.png)

## Notes
While working collaboratively on Live Share, all the changes will appear as if they had been made by the host of the session (the driver). Thus, remember to appropriately indicate that the work was done as a team in the [commit message](https://docs.github.com/es/github/committing-changes-to-your-project/creating-and-editing-commits/creating-a-commit-with-multiple-authors) :D.

## More information
For more information or if you encounter a problem while installing or using Live Share, visit these pages:
- https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare
- https://docs.microsoft.com/en-us/visualstudio/liveshare/
