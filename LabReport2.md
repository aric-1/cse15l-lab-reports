# ChatServer Code and Screenshots
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {

    String s = "";

    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("&");
            if (parameters[0].contains("s=") && parameters[1].contains("user=")) {
                String message = parameters[0].split("=")[1];
                String user = parameters[1].split("=")[1];
                s = s + user + ": " + message + "\n";
                return s;
            }
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

Screenshot 1:
![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/17d8af66-792f-45bc-b232-bd1bb3095192)
Methods called: 
  `main(String[] args` in the `ChatServer` class is called first, which then calls the `start` method in the `Server` class, which eventually calls
  
  
  The `handleRequest` method in `Handler` is called. The methods called in the `Server` class are not part of my code.
  
Arguments, fields: `URI url` is passed  into the `handleRequest` method, which contains the instructions for the program to follow. 
The field `s` in the  `handler` class keeps track of the messages that have been sent. As a result of this call, the `s` field is changed
from `yash: How are you\nyash: good\n` to `yash: How are you\nyash: good\nyash: I like burgers\n`, since the program adds 
a new message, colon and space, username, and newline to the string `s` from the `url` input.


Screenshot 2:
![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/cf93da52-f6f1-470d-890d-27bb54782dc0)

Arguments, fields: `URI url` is passed  into the `handleRequest` method, which contains the instructions for the program to follow. 
The field `s` in the  `handler` class keeps track of the messages that have been sent. As a result of this call, the `s` field is changed
from `yash: How are you\nyash: good\nyash: I like burgers\n` to 
`yash: How are you\nyash: good\nyash: I like burgers\naric: In my opinion, the Philadelphia 76ers are not making it past the second round\n`, 
since the program adds a new message, colon and space, username, and newline to the string `s` from the `url` input.

# Part 2

Private key for SSH into ieng6:
![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/7210d6d4-965d-4852-8e85-e51377eba080)


Public key:
![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/6b11e4aa-1a96-4e3e-9799-084d8c502d7b)


Logging in without signing into ieng6:
![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/fdcc5338-3d7a-489b-910f-1422777da522)

## Something new I learned:

I learned how to create a public and private SSH key using the ssh-keygen command. I also learned where the files should go
and how to set up the keys with a server.




