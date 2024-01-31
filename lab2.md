# **Lab 2 Report**

## **Part 1**
1. ChatServer Code File
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String message = null;
    String user = null;
    String memory = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("&");

            String[] userMessage = parameters[0].split("=");
            if (userMessage[0].equals("s")) {
                message = userMessage[1];
            }

            String[] userName = parameters[1].split("=");
            if (userName[0].equals("user")) {
                user = userName[1];
            }

            memory += String.format("%s: %s\n", user, message);
            return memory;

        }

        return "404 Not Found!";

    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

2. Output: Message 1
> <img width="604" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/12e4a4db-37e5-423b-bc49-a86aaf7e2b01">

The method `String handleRequest(URI url)` is called when we add `/add-message?s=Hello&user=jpolitz` to the port URL. As shown in the code screenshots, the URL is first split by the `&` symbol and stored into the String array `parameters`. Afterwards, each `parameter` index is split by the `=` sign and then stored into the String array `userName`. The value `Hello` at `userName[0]` and the value `jpolitz` at `userName[1]` are then stored into the appropriate instance variables, `message` and `user`, which changes the instance variables' values from `null` to `Hello` and `jpolitz`. Lastly, the relevant instance variable `memory` is changed from empty string to store the string formatted `user` and `message`. Then, it is returned to the web server.

2. Output: Message 2
> <img width="599" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/3426da9b-5f2d-4475-83eb-05fffd575cd0">

Similar to the previous screenshot, the method `String handleRequest(URI url)` is called when we add `/add-message?s=How are you&user=yash` to the port URL. The same arguments `.split()` and `.equals()` are applied, and the URL following `/add-messages` is split by the `&` sign and then by the `=` sign. The instance variable `user`'s value then changed from `jpolitz` from the last iteration to `yash` when we set the variable to now equal to the value at `userName[0]`. Similarly, the instance variable `message` is changed from `Hello` to `How are you` when we set the variable to now equal the value at `userName[1]`. Then, the value of the instance variable `memory` is changed when we add the new String formatted `user` and `message` to the variable.

## **Part 2**
1. The absolute path to the ***private*** key
> <img width="314" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/60e9b790-5c89-48d0-9e1a-9135283fd0d6">

2. The absolute path to the ***public*** key
> <img width="341" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/f7b75176-757a-4d14-b188-be72652dc334">

3. Terminal interaction ***without*** being asked for a password
> <img width="519" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/1efaa69e-2621-4fa0-b99a-84456bb8253c">

## **Part 3**
Prior to week 2, I did not know how to create a web server out of my code. As a result, the lab session that week taught me new knowledge I've never been exposed to before. To be specific, I didn't know about the methods `.getPath()` and prior to CSE15L I was unfamiliar with what each character in a URL might mean. (For example, `?` stands for query and can be used to run certain code actions.) As a result, I learned that simply splitting the URL into different key words that follow a query, I can call upon different methods within my code. Furthermore, I can connect to a web server by running my file and choosing a web server that was within port range.
