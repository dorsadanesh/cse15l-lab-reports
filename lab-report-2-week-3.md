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
            if (url.getPath().equals("/")) {
                return String.format("Word List: %s", addedString.toString());
            }
            else if (url.getPath().equals("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    addedString.add(parameters[1]);
                    return String.format("String added!");
                } 
                else {
                    return "Nothing to add";
                }

            } else if (url.getPath().equals("/search")) {
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
Once the server is running, the browser will open to this: <img width="1333" alt="Screen Shot 2022-10-28 at 8 24 50 PM" src="https://user-images.githubusercontent.com/114564837/198804257-285bd4bf-9e38-4536-aed4-ef009dce85e9.png">

Then, adding a string, such as hello, should look like this: <img width="1360" alt="Screen Shot 2022-10-13 at 9 11 24 AM" src="https://user-images.githubusercontent.com/114564837/195649960-8dd23d8d-45d0-4b36-b934-9f616bc7f239.png">
The add is a result of the if loop beginning on line 10 of the SearchEngine code. It looks for /add in the url, followed by s= and a string. If it is valid, the string will be added to the arraylist called addedString and the browser will show the message "String Added!" as seen above in the screenshot.

The /search?s= calls the handlerequest method. It will search for the string following the = sign. In the browser, it should look like this: 

## Part Two
**Two bugs from Week 3 Lab files:**
1. * The failure-inducing input (the code of the test):
    ```
    @Test
    public void reverseTests() {
        int[] input1 = {4,5,4};
        assertArrayEquals(new int[]{4,5,4}, ArrayExamples.reversed(input1));
    }
    ```
   * The symptom (the failing test output):
    Expected: 4
    Actual: 0
   * The bug (the code fix needed):
   * Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?
2. * The failure-inducing input (the code of the test):
    ```
    @Test
    ```
   * The symptom (the failing test output)
   * The bug (the code fix needed)
   * Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?
