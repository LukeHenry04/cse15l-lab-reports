# Lab Report 5
### Luke Henry

***

**Creating a bash script for Lab Report 4**

The challenge was to complete the following steps as fast as possible, after creating a new fork of the [Lab7 github repo](https://github.com/ucsd-cse15l-w23/lab7):

- Log into ieng6
- Clone your fork of the repository from your Github account
- Run the tests, demonstrating that they fail
- Edit the code file to fix the failing test
- Run the tests, demonstrating that they now succeed
- Commit and push the resulting change to your Github account

After logging into ieng6, I made the bash file `challenge.sh`, with the code:

``` 
git clone git@github.com:LukeHenry04/lab7.git
cd lab7

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

vim ListExamples.java

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

git add ListExamples.java
git commit -m "fixed error in ListExamples.java"
git push

```

Now, the only commands I need to run are:

- `ssh cs15lwi23akd@ieng6.ucsd.edu` in my local terminal
- `bash challenge.sh`
- and the keys `a<backspace><backspace>2<esc>:wq` to edit the file.

The process now looks like this:

### Step 1) Log into ieng6

Keys pressed: `<up><enter>`

The command `ssh cs15lwi23akd@ieng6.ucsd.edu` was the last command in my history, so I pressed `<up>` and then ran it. 

![image of ssh login](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/SSH.png)

### Step 2) Run challenge.sh

Keys pressed: `<up><up><up><up><enter>`

The command `bash challenge.sh` was 4th in my histroy so I pressed `<up>` 4 times and ran it.

It cloned the github repository, and ran the junit tests in the `lab7/` directory, which fail.

It then runs the command `vim ListExamples.java` and waits for me to edit the code.

![Image of failed tests](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/failures.png)

### Step 3) Edit ListExamples.java

Keys pressed:  `a<backspace><backpace>2<esc>:wq<enter>`

I first press `a` to edit the file, then press `<backspace>2` to change `index1` to `index2`.

Then I press `<esc>:wq<enter>` to write to the file and exit the vim command. 

![Image of vim editing](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/vim.png)

`challenge.sh` then continues running. It runs the tests again, which now pass, and then commits and pushes the changes to the github repository. 

![image of passed tests and commit and push](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/commit.png)


