# Week 1 Lab Report - Luke Henry
**Contents:**
- [Installing Visual Studio Code](https://lukehenry04.github.io/cse15l-lab-reports/Week1_Lab_Report.html?#installing-visual-studio-code)
- [Remotely Connecting](https://lukehenry04.github.io/cse15l-lab-reports/Week1_Lab_Report.html?#remotely-connecting)
- [Running Commands](https://lukehenry04.github.io/cse15l-lab-reports/Week1_Lab_Report.html?#running-commands)
***

## Installing Visual Studio Code
The first step for remote access is to install Visual Studio Code.

Go to **https://code.visualstudio.com** and download the appropriate version of VS Code for your operating system. Run the installer and follow the setup intructions. Open Visual Studio Code. Your window should look like this:

![Screenshot of VS Code window](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_Code.png)

Click **Terminal** --> **New Terminal**. You'll be using the terminal to remotely connect and run commands.

![Screenshot of VS Code Terminal](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_CodeTerminal.png)

## Remotely Connecting
In order to remotely connect on Windows, you will need to install git. You can download [**Git for Windows** here](https://gitforwindows.org/), then run the installer. 

Once git is installed, open the Visual Studio Code terminal and open a **git bash** terminal using the dropdown menu next to the '**+**' icon (see image below):

![Screenshot of git bash terminal](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_GitBash.png)

Next run run the command `$ ssh cs15lwi23zz@ieng6.ucsd.edu`, repacing '**zz**' with the last letters of your course username:

![Terminal login command image](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_RemoteLogin.png)

Next enter your password. If you are successfully connected, your terminal will show similar text to the image below:

![Successful login terminal image](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_RemoteLoginSuccess.png)

## Running Commands
Once you're connected, you can begin to run some commands.

The command `pwd` stands for "**Print Working Directory**". Running it will tell you what directory you are currently working in. 

![Image of pwd command](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_CommandPWD.png)

To change the current working directory, you can use the `cd` command followed by an aboslute or relative path. (`cd` stands for "**Chage Directory**".) For example, `cd ..` will change the working directory to the parent directory.

The command `ls`, for "**list**", lists the contents of the working directory.

![Image of cd and ls commands](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_CommandCD_LS.png)

Finally, you can log out with the command `exit`:

![Image of exit command](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_CommandEXIT.png)

You can also run these commands locally on your own computer. For example, after logging out, running `pwd` will show the current working directory as a folder on your computer. You can use `cd Documents` for example, to change your working directory to your documents folder and `ls` to list its contents:

![Image of local commands](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_CommandLOCAL.png)




