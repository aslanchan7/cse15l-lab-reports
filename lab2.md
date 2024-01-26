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

   For `main()`, it takes in the port number. For `handleRequest()`, it takes in the URL. Under `handleRequest()`, there is a field to store the full string of all the messages, and fields to store strings for the `user` and `message`.

3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.

   Initially, the string fields for the `message` and `user` are set to an empty string. But as the program runs, the `message` and `user` fields take the appropriate values from the query. The `fullString` field stores all the messages and is used to print the whole conversation.

**Screenshot 2**

![Image](/lab_report_2_ss2.png)

1. Which methods in your code are called?
 
   This time, the `main()` method is not called because the server is already running. However the `handleRequest()` method is run again.

2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?

   For `handleRequest()`, it takes in the new URL. In it, the fields `user` and `message` are set to an empty string once again. However the field `fullString` still stores the previous message.

3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.

   In this case, the new message is appended to `fullString` and this is returned to produce the output shown in the screenshot above.

## **Part 2**

**Private Key**

![Image](/lab_report_2_ss3.png)

Absolute Path: `C:/Aslan Chan/Users/.ssh/id_rsa`

**Public Key**

![Image](/lab_report_2_ss4.png)

Absolute Path: `asc010@ieng6.ucsd.edu:~/.ssh/authorized_keys/id_rsa.pub`

**Logging in Without Entering Password**

![Image](/lab_report_2_ss5.png)

## **Part 3**

**What Have I Learned?**

From labs in week 2 and week 3, something new I learned was setting up to run a website locally. I also learned how to log in to my school's server through my own laptop. A new command I learned in the terminal is `man` which is very helpful, especially if I don't know or forget how to use a certain command. 
