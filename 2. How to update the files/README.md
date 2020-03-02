# SpotMicroAI

Hello, I'm Fran and i'm going to guide you in the steps needed send files to your RaspberryPi inside your SpotMicroAI.

This part of the tutorial assume you already have the RaspberryPi ready in your spotmicro. If not, go back to the previous tutorial: [1. Prepare your RaspberryPi](https://gitlab.com/custom_robots/spotmicroai/basic/-/tree/master/1.%20Prepare%20your%20RaspberryPi)

# Transfering files in and out

We have enabled the SSH service in our SpotMicroAI, so, we are ready to transfer files from our computer conviniently.

To do so we are going to use a software called FileZilla Client, you can download it from: https://filezilla-project.org/download.php?type=client

FileZilla Client installation may suggest you to install third party software, skip it. We just need FileZilla Client.

Open the client to see it, it has 2 sides, left and right.

![filezilla-client-first-window](filezilla-client-first-window.JPG)

* Left side is your computer
* Right side is your SpotMicroAI

Write your SpotMicroAI ip address, user **pi**, password **spotmicroai**, port **22** and press QuickConnect!

![filezilla-client-login-spotmicro](filezilla-client-login-spotmicro.JPG)

FileZilla will offer you to save the password, go for it.

You will see the SD card folders in the right panel. Note that you will not see any spotmicroai folder (the ones marked in yellow in the picture), if you didn't finish the tutorials yet.

![filezilla-client-right-panel](filezilla-client-right-panel.JPG)

Now, you can drag and drop files in and out from SpotMicroAI as you need.

Try to create a folder and upload/download a file if you like

# SpotMicroAI

**You are all set!**
