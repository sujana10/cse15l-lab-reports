## Week 1 Lab Report
**Sujana Sreenivasan**

This is a simple tutorial for logging into a course-specific account on `ieng6` for CSE 15L. It will cover installing Visual Studio Code onto your device, remotely connecting to your account from your personal computer, and trying out commands in the terminal.

### Installing Visual Studio Code

I previously had VS Code downloaded on my computer from another class, but the process is really quite simple. Just visit the [VS Code Website](https://code.visualstudio.com/) and follow the instructions to get the app on your computer. I have a MacOS, so I downloaded that version of the app. Once it's downloaded, opening up the app should give you something like the screenshot below:

![image1](./Screen%20Shot%202023-01-11%20at%202.39.54%20PM.png)

### Remotely Connecting

The first thing you should do before remotely connecting is make sure you have `git` installed on your computer; Mac users already have this, but Windows users should follow the instructions at [this link](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994).

Then, look up your CSE 15L course-specific account [here](https://sdacs.ucsd.edu/~icc/index.php). Follow the instructions at [this link](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit) in order to reset the password to this account so you can begin connecting remotely. After doing that, open a terminal in VS Code and enter the command: 

`ssh <CSE 15L-specific account>`

and answer 'yes' to any prompted messages when connecting for the first time. After logging in, your terminal should look similar to this for your specific account:

![](https://github.com/sujana10/cse15l-lab-reports/blob/38f15a4134fbbfbc82b4cc618ac630c2984dd184/Screen%20Shot%202023-01-12%20at%202.34.35%20PM.png)

### Trying Terminal Commands

After I logged in for the first time, I played around with different commands in my terminal like `cd`, `pwd`, `ls <directory>`, and so on. This produced a variety of outputs, including some error messages! For example, I got an `Error` when I tried accessing another user's directory. Also, the command `exit` will log you out of the remote server. Here is a screenshot of some example commands and their outputs:

![](https://github.com/sujana10/cse15l-lab-reports/blob/38f15a4134fbbfbc82b4cc618ac630c2984dd184/Screen%20Shot%202023-01-12%20at%202.35.05%20PM.png)

#### *The End!*



