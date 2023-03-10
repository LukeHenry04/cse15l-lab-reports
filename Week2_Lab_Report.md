# Week 2 Lab Report
### Luke Henry
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

The url path and query `/add-message?s=Hello` adds the string after `"s="`, in this case `Hello`, to the string:

![Hello Image](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/Hello.png)

The method `handleRequest(URI url)` is called, where `url` is an object that contains the domain, path, and query of the url shown above.

The path is acessed via the method `url.getPath()` which returns the string `"/add-message"`

If the path contains `"/add-message"`, which it does in this case, the method `url.getQuery() is used to get the part of the url after the `"?"`, in this case it returns `"s=Hello"`.

The string `"s=Hello"` is then split into the strings `"s"` and `"Hello"` using the method `.split("=")` and stored as elements `0` and `1` of the string array `parameters`

`"Hello"` is then added to the main string `text` with the new line character, `'\n'`, as shown in the above screenshot. 

***

A different url path can be used to add different strings. Changing the string after `"s="` to `How are you` makes the url path and query: `/add-message?s=How are you`, which now adds 'How are you' to the string, `text`, with a new line. The result is a string containing two lines, one with the initial `Hello` and the second with the line `How are you`, shown below:


![How Are You Image](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/HowAreYou.png)

The method `handleRequest(URI url)` is called again, with url now containing the domain, path, and query of the new url above.

`url.getPath()` now returns the new path, `"/add-message"`.

`url.getQuery` now returns the string in the path after the question mark, `"s=How are you"`, which is split into the `parameters` array.

The string `"How are you"` followed by a new line character `'\n'` is then added to the main string `text` containing `"Hello"+'\n'`.

The result is two lines, with "Hello" and "How are you", shown in the screenshot above.

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

![ScreenshotTerminal](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/TerminarErrorFull.png)

Where the symptom is that the first element of the returned array is `0`, when it should be `4`.

The bug was that, in the line `arr[i] = newArray[arr.length - i - 1];`, `arr` and `newArray` are switched, so that the elements of the initial array are changed, and set to 0, the elements of the new empty array. It also returns the original array instead of the new array in the line `return arr`. 

The code change needed to fix the bug was switching `arr` and `newArray` and returning `newArray`.

Before the code was:
```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
After fixing the bug, the code is now:
```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

## Part 3 - What I Learned

One important thing I learned in lab during week 2 was how URLs are stuctured and used when running web servers. For example, in the url `google.com/search?q=searchTerm`, `google.com` is called the **domain**, `/search` is called the **path**, and `?q=searchTerm` is called the **query**. A web server can use the path and query to preform specific functions, such as the numberSever and searchServer in lab, which used specific paths and queries to alter or search through data in the server. 
