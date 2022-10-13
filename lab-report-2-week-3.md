# Lab Report 2
## Part One
Simplest Search Engine Code:
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {

    public String handleRequest(URI url) {
        ArrayList<String> addedString = new ArrayList<String>();
        ArrayList<String> foundString = new ArrayList<String>();
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    addedString.add(parameters[1]);
                    return String.format("String added!");
                } 
                else {
                    return "Nothing to add";
                }

            } else if (url.getPath().contains("/search")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    for(String s : addedString){
                        if (s.contains(parameters[1])){
                            foundString.add(s);
                        }
                    }
                }
                if(foundString.size() != 0) {
                    return String.format(foundString.toString());
                }
                else{
                    return "none";
                }
            }
            else{
                return "none";
            }
        }
    }


class SearchEngine {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
Once the server is running, the browser will open to this: <img width="1363" alt="Screen Shot 2022-10-13 at 9 07 10 AM" src="https://user-images.githubusercontent.com/114564837/195648918-26a82f64-a684-4710-afb7-383fa5917d68.png">

Then, adding a string, such as hello, should look like this: <img width="1360" alt="Screen Shot 2022-10-13 at 9 11 24 AM" src="https://user-images.githubusercontent.com/114564837/195649960-8dd23d8d-45d0-4b36-b934-9f616bc7f239.png">
The add is a result of the if loop beginning on line 10 of the SearchEngine code. It looks for /add in the url, followed by s= and a string. If it is valid, the string will be added to the arraylist called addedString and the browser will show the message "String Added!" as seen above in the screenshot.

The query

## Part Two
**Two bugs from Week 3 Lab files:**
1. * The failure-inducing input (the code of the test)
   * The symptom (the failing test output)
   * The bug (the code fix needed)
   * Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?
2. * The failure-inducing input (the code of the test)
   * The symptom (the failing test output)
   * The bug (the code fix needed)
   * Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?
