# Part 1
### This is my code of StringServer:  
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;

    public static String display = "";

    public String handleRequest(URI url)
    {
        if (url.getPath().equals("/"))
        {
            return display;
        } else
        {
            if (url.getPath().contains("/add-message"))
            {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s"))
                {
                    display += "\n" + parameters[1];
                    return display;
                }
            }
        }
        return "404 Not Found!";
    }
}

class StringServer {
    public static void main(String[] args) throws IOException
    {
        if (args.length == 0)
        {
            System.out.println(
                "Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
### First use of add-message:  
![image](https://user-images.githubusercontent.com/118026674/215015252-27d20c3d-4a8c-444e-b03c-a4d6c7413603.png)  
Here, the method handleRequest is called.  
After entering the second if statement (if (url.getPath().contains("/add-message"))), it adds "\n handsome" to String display, and later shows this string.  
URI url becomes http://localhost:8888/add-message?s=handsome; String[] parameters gets two values: "s" and "handsome"; String display is appended by "\n handsome".  
### Second use of add-message:  
![image](https://user-images.githubusercontent.com/118026674/215016483-92a9498e-5b08-4f65-8d42-c8dd3431d22d.png)  
Here, the method handleRequest is called.  
After entering the second if statement (if (url.getPath().contains("/add-message"))), it adds "\n as" to String display, and later shows this string.  
URI url becomes http://localhost:8888/add-message?s=as; String[] parameters gets two values: "s" and "as"; String display is appended by "\n as".  
# Part 2  
Actual code:
```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}
```  
Failure-inducing input:
```
@Test
public void testReverseInPlace2()
{
  int[] input1 = {12, 34, 56};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{56, 34, 12}, input1);
}
```  
Input that doesn't induce a failure:  
```
public void testReverseInPlace1()
{
  int[] input1 = {3};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{3}, input1);
}
```  
Result of running JUnit:  
![image](https://user-images.githubusercontent.com/118026674/215018296-542baa7a-7119-47a1-8556-d780a09a17fe.png)  
To kill this nasty bug, we need to change:  
```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}
```  
To:  
```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length / 2; i ++) {
    int temp = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = temp;
  }
}
```  
By changing our code, we now are swaping the data, instead of overriding the data, and therefore we fixed the bug.  
# Part 3  
In week 2 and 3, I learned how to create my own website, which is something that I have never done. In the past, I mostly did competitive programming, and the result I got was either pass or fail, not rewarding. Creating my own website makes me feel that I accomplished something, that I have left a mark of Benny on the internet (although it is only on the UCSD internet).


















