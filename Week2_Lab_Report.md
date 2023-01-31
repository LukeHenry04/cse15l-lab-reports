# Week 2 Lab Report
***

## Part 1 - Running a Web Server
StringServer keeps track of a string and allows the user to add new lines to the string with the url path `/add-messages?s=<string>`, where <string> is the added line. 
The code iplememnting StringServer is shown below:
```
import java.io.IOException;
import java.net.URI;

class StringHandler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
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

## Part 2 - Debugging and Testing Code

## Part 3 - What I Learned
