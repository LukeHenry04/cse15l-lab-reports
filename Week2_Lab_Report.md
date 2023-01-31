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

The path `/add-message?s=Hello` adds 'Hello' to the string:

![Hello Image](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/Hello.png)
The method `handleRequest(URI url)` is called, where `url` is an object that contains the path of the url, which is acess via the method `url.getPath()`.

Then, using the path `/add-message?s=How are you` adds 'how are you' to the string with a new line:

![How Are You Image](https://raw.githubusercontent.com/LukeHenry04/cse15l-lab-reports/main/HowAreYou.png)

## Part 2 - Debugging and Testing Code

## Part 3 - What I Learned
