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



## **Part 2**

## **Part 3**
