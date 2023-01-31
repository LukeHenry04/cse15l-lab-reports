# Week 2 Lab Report
***

## Part 1 - Running a Web Server
StringServer keeps track of a string and allows the user to add new lines to the string with the url path `/add-messages?s=STRING`, where `STRING` is the added line, which is appened to the original string with a new line, `'\n'`, character.

The code implementing StringServer is shown below:
```
import java.io.IOException;
import java.net.URI;

class StringHandler implements URLHandler {
    String text = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return text;
        }else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    text += parameters[1] + '\n';
                    return text;
                }
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new StringHandler());
    }
}
```

***

The path `/add-message?s=Hello` adds 'Hello' to the string:


![Hello Image](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/Hello.png)

The method `handleRequest(URI url)` is called, where `url` is an object that contains the path of the url.

The path is acessed via the method `url.getPath()` which returns the string `"/add-message?s=Hello"`

If the path contains `"/add-message"`, which it does in this case, the method `url.getQuery() is used to get the part of the path after the `"?"`, in this case it returns `"s=Hello"`.

The string `"s=Hello"` is then split into the strings `"s"` and `"Hello"` using the method `.split("=")` and stored as elements `0` and `1` of the string array `parameters`

`"Hello"` is then added to the main string `text` with the new line character, `'\n'`. 

***

Now, the path `/add-message?s=How are you` adds 'How are you' to the string with a new line:


![How Are You Image](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/HowAreYou.png)

The method `handleRequest(URI url)` is called again, with url now containing the new path.

`url.getPath()` now returns the new path, `"/add-message?s=How are you"`.

`url.getQuery` now returns the string in the path after the question mark, `"s=How are you"`, which is split into the `parameters` array.

The string `"How are you"` followed by a new line character `'\n'` is then added to the main string `text` containing `"Hello"+'\n'`.

The result is two lines, with "Hello" and "How are you".

***

## Part 2 - Debugging and Testing Code

The program `ArrayExamples.java` contained bugs in the `int[] reversed(int[] arr)` method.

A faliure inducing input, as a JUnit test, is:

```
int[] input2 = {1, 2, 3, 4};
assertArrayEquals(new int[]{4, 3, 2, 1}, ArrayExamples.reversed(input2));
```

An input that doesn't incude failiure, as a JUnit test, is:

```
int[] input1 = { };
assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
```

Running both tests fails the first test, giving the result:

![ScreenshotTerminal](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/TerminarError.png)

Where the symptom is that the first element of the returned array is `0`, when it should be `4`.





## Part 3 - What I Learned
