# **Lab Report 2**

## **Part 1**

```
import java.io.IOException;
import java.net.URI;

class ChatServerHandler implements URLHandler {
    String fullString = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return "Try '/add-message?s=<message>&user=<user>'";
        } else if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("&");
            String message = parameters[0].substring(2);
            String user = parameters[1].substring(5);

            if (user.equals("") || message.equals("")) {
                return "Try '/add-message?s=<message>&user=<user>'";
            } else {
                fullString += String.format("%s: %s\n", user, message);
            }

            return fullString;
        } else {
            return "Try '/add-message?s=<message>&user=<user>'";
        }
    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new ChatServerHandler());
    }
}
```

**Screenshot 1**

![Image](/lab_report_2_ss1.png)

1. Which methods in your code are called?
   The `main()` and `handleRequest()` methods are called.

2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?
   For `main()`, it takes in the port number. For `handleRequest()`, it takes in the URL. Under `handleRequest()`, there is a field to store the full string of all the messages, and fields to store strings for the user and message.
How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.

## **Part 2**

## **Part 3**
