# Lab Report 5
### Luke Henry

***

**Creating a bash script for Lab Report 4**

The challenge was to complete the following steps as fast as possible:

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
- and the keys `a<backspace>2<esc>:wq` to edit the file.


