```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler{
    String str = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("&");

            String[] userParam = parameters[1].split("=");
            String[] messageParam = parameters[0].split("=");
            String user = userParam[1];
            String message = messageParam[1];
            str += String.format("%s: %s\n", user, message);
            return str;
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
