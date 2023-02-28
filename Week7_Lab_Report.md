# Week 1 Lab Report - Luke Henry

***

(Steps 1 through 3 were preparation for the following steps: )

## Step 4) Log into ieng6

Keys pressed: `<up><enter>`

The command `ssh cs15lwi23akd@ieng6.ucsd.edu` was the last run command in my local terminal, so i pressed the `<up>` to access it.

Image of ssh log in command

## Step 5) Clone your fork of the repository from your Github account

Keys pressed: `<up><up><up><up><enter>`, `<up><up><up><up><enter>`

The command `git clone git@github.com:LukeHenry04/lab7.git` was 4th in my command history, so I used `<up>` 4 times to find it and then ran it.

The command `cd lab7` was then 4th in my history, so I pressed `<up>` 4 times and then ran it.

Image of git clone command

## Step 6) Run the tests, demonstrating that they fail

Keys pressed: `<up><up><up><up><up><up><up><up><up><up><up><enter>`, `<up><up><up><up><up><up><up><up><up><up><up><enter>`

The command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` was 11th in my history so I pressed `<up>` 11 times and ran it.

Then the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` was 11th, so I pressed `<up>` 11 times again and ran it.

The result shows 1 test failed.

Image of running failed tests

## Step 7) Edit the code file to fix the failing test

Keys pressed: `<up>`x15`<enter>`, `<a><backspace><backspace><2><space>`, `<esc><:><w><q><enter>`

The command `vim ListExamples.java` was then 15th in my history, so I used `<up>` 15 times and ran it.

My cursor's position was already right after the error, so I pressed `<a>` to edit at the cursor position, then editited `index1` to `index2` in ListExamples.java.

After edititing, I used `<esc>` and then `:wq` to write the new changes and then exit the `vim` command.

Image of vim command

## Step 8) Run the tests, demonstrating that they now succeed

Keys pressed: `<up><up><up><enter>`

The command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` was 3rd in my history, so I pressed `<up>` 3 times and ran it.

The command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` was then 3rd in my history so I pressed `<up>` 3 times and ran it.

This time, the tests all passed.

Image of passed tests

## Step 9) Commit and push the resulting change to your Github account

Keys pressed: `<up>`x14`<enter>`, `<up>`x14`<enter>`, `<up>`x14`<enter>`

The command `git add ListExamples.java` was 14th in my history, so I pressed `<up>` 14 times and ran it.

The command `git commit -m "fixed error in ListExamples.java"` was then 14th in my history, so I pressed `<up>` 14 times and ran it.

Then the command `git push` was 14th, so I again pressed `<up>` 14 times and ran it.

This added the file ListExamples.java and commited it, then pushed the commit to the github repository fork.

Image of github commands
