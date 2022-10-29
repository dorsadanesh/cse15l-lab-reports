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
            else if (url.getPath().contains("/add")) {
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
                        return String.format(foundString.toString());
                    }
                }
            } 
            return "none";
            
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

Then, finding an added string will look like this: <img width="1338" alt="Screen Shot 2022-10-28 at 10 38 19 PM" src="https://user-images.githubusercontent.com/114564837/198815814-dd041663-609d-4c5e-8c4c-67d5e6a3ec22.png">
With the added string included in the brackets.

## Part Two
**Two bugs from Week 3 Lab files:**
1. * The failure-inducing input (the code of the test):
    ```
    @Test
    public void testReversed2() {
        int[] input1 = {1,2,3,4,5};
        assertArrayEquals(new int[]{5,4,3,2,1}, ArrayExamples.reversed(input1));
    }
    ```
   * The symptom (the failing test output):
    Expected: 5
    Actual: 0
   * The bug (the code fix needed):
    Instead of copying arr into newArray, the code copies newArray into arr, and it returns arr when it should return new Array. To fix, change
    ```
    static int[] reversed(int[] arr) {
        int[] newArray = new int[arr.length];
        for(int i = 0; i < arr.length; i += 1) {
            arr[i] = newArray[arr.length - i - 1];
        }
        return arr;
    }
    ```
    to
    ```
    static int[] reversed(int[] arr) {
        int[] newArray = new int[arr.length];
        for(int i = 0; i < arr.length; i += 1) {
            newArray[i] = arr[arr.length - i - 1];
        }
        return newArray;
    }
    ```
   * Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?
    The expected is because newArray is initialized with size 5, but nothing is copied over. This results in an empty input1 (aka the actual value, 0).
2. * The failure-inducing input (the code of the test):
    ```
    @Test
    public void testingFilter() {
        List<String> newList = new ArrayList<>();
        newList.add("hello");
        newList.add("it's");
        newList.add("nice");
        newList.add("to");
        newList.add("meet");
        newList.add("you");
        newList.add("dorsa");
        List<String> expected = new ArrayList<>();
        expected.add("hello");
        expected.add("dorsa");
        StringChecker sc = new Checking();
        assertEquals(expected, ListExamples.filter(newList, sc));
    }
    ```
   * The symptom (the failing test output):
    Expected: (hello, dorsa)
    Actual: (dorsa, hello)
   * The bug (the code fix needed):
    To fix, change
    ```
    result.add(0, s); 
    ```
    to 
    ```
    result.add(s);
    ```
   * Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?
    In line 14 in ListExamples.java, it adds the new string to the front of the list instead of the end, causing them to appear in the wrong order.
    
