# Creating a Bootable Drive
1. Dowload the version of Ubuntu you want
1. Install software like [Etcher](https://etcher.balena.io/#download-etcher) if you don't already have it
    1. if it gives you a `.AppImage` file, click on *Properties*. Click on *Permissions* and click on *Allow executing the file as a program*.
    1. In the command line, run `chmod u+x path/to/file.AppImage`
1. Plug in your drive
1. Use Etcher to turn the drive into an installer for the software
1. Go to the computer you want to install Ubuntu on, and plug the drive in
1. Restart the computer, and it should grab on to the drive.
    1. If it doesn't, restart again and hold `F12` when the logo screen comes up.
1. Follow the instructions, and enjoy.