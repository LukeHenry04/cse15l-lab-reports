# Week 1 Lab Report - Luke Henry
**Contents:**
- [Installing Visual Studio Code](https://lukehenry04.github.io/cse15l-lab-reports/Week1_Lab_Report.html?#installing-visual-studio-code)
- [Remotely Connecting](https://lukehenry04.github.io/cse15l-lab-reports/Week1_Lab_Report.html?#remotely-connecting)
- [Running Commands](https://lukehenry04.github.io/cse15l-lab-reports/Week1_Lab_Report.html?#running-commands)

***

## Installing Visual Studio Code
The first step for remote access is to install Visual Studio Code.

Go to **[Visual Studio Code](https://code.visualstudio.com)** and download the appropriate version of VS Code for your operating system. Run the installer and follow the setup intructions. Open Visual Studio Code. Your window should look like this:

![Screenshot of VS Code window](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_Code.png)

Click **Terminal** --> **New Terminal**. You'll be using the terminal to remotely connect and run commands.

![Screenshot of VS Code Terminal](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_CodeTerminal.png)

## Remotely Connecting
In order to remotely connect on Windows, you will need to install git. If you do not have Windows, you do not need to install git or open a git bash terminal. Mac and Linux users can skip this step.

You can download [**Git for Windows** here](https://gitforwindows.org/), then run the installer. 

Once git is installed, open the Visual Studio Code terminal and open a **git bash** terminal using the dropdown menu next to the '**+**' icon (see image below):

![Screenshot of git bash terminal](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_GitBash.png)

Next, you will need find your CSE15L account. You can look up your account [**Here**](https://sdacs.ucsd.edu/~icc/index.php).

![Account Lookup](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/AccountLookup.png)

Click on the **Cse15lwi23--** account under **Additional Accounts**. Then click **Change Password**:

![Password change](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/AccountPasswordChange.png)

Change your course password to a strong complex password that meets the requirements.

***
Next, in Visual Studio Code:

Run the command `$ ssh cs15lwi23zz@ieng6.ucsd.edu`, repacing '**zz**' with the last letters of your course username:

![Terminal login command image](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_RemoteLogin.png)

Next enter your password. 

You may recieve the confiration message below:
```
⤇ ssh cs15lwi23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```
If this is your first time logging in, you will need to type yes to connect.

If you are successfully connected, your terminal will show similar text to the image below:

![Successful login terminal image](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_RemoteLoginSuccess.png)

## Running Commands
Once you're connected, you can begin to run some commands.

The command `pwd` stands for "**Print Working Directory**". Running it will tell you what directory you are currently working in. 

![Image of pwd command](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_CommandPWD.png)

To change the current working directory, you can use the `cd` command followed by an aboslute or relative path. (`cd` stands for "**Change Directory**".) For example, `cd ..` will go to the parent directory of the current working directory.

The command `ls`, for "**list**", lists the contents of the working directory.

![Image of cd and ls commands](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_CommandCD_LS.png)

Finally, you can log out with the command `exit`:

![Image of exit command](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_CommandEXIT.png)

You can also run these commands locally on your own computer. For example, after logging out, running `pwd` will show the current working directory as a folder on your computer. You can use `cd Documents` for example, to change your working directory to your documents folder and `ls` to list its contents:

![Image of local commands](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/VS_CommandLOCAL.png)




