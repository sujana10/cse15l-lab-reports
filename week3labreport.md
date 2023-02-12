## Week 3 Lab Report
**Sujana Sreenivasan**

### Part 1

Here are some screenshots for a program I wrote called StringServer.java. The goal of this program is to act as a web server that keeps track of a single string that gets added to by incoming requests, in the form of a path that looks like "/add-message?s=(string)".

![image1](./Screen%20Shot%202023-02-11%20at%203.31.00%20PM.png) 
  
The first screenshot shows the code itself and how the program is implemented. It utilizes the pre-created file Server.java to properly handle the URL and launch the server. The next screenshots show the web server in action by testing it using URLs from the browser. 

![image2](./Screen%20Shot%202023-02-11%20at%203.38.38%20PM.png)

This screenshot shows the commands that were used in the terminal to launch the StringServer. These commands call the main method in the StringServer class to start a web server using the port provided as an argument, which is 35000 in this case. No values of the main class field `runningString` were changed at this point, because the terminal commands only work to launch the server in a browser.

![image4](./Screen%20Shot%202023-02-11%20at%203.37.37%20PM.png)
![image5](./Screen%20Shot%202023-02-11%20at%203.37.58%20PM.png)
  
The last two screenshots show the output of actually using the StringServer to handle and manage requests. Each of the two requests works the same way, but the second request adds to the first request to create a running string. To obtain the above output in the first screenshot, the browser URL is passed into the method handleRequest(URI url) as a URI argument, which works to isolate the string message from the URL query and add it to the running string output. This changes the value of the main data field `runningString` because the string "\nGood afternoon!" is added to that originally empty string. For the second screenshot, handleRequest(URI url) does the same thing with the new URL, but instead adds the string "\nHave a great day :)" to the preexisting string, setting the new value of `runningString` equal to "\nGood afternoon!\nHave a great day :)". This corresponds to the final output of the browser tests.
  
### Part 2
Below I will be showing some code for a method reverseInPlace() that reverses the order of an integer array.
  
Failure inducing input: 
``` 
@Test
  public void testReverseInPlace() {
    int[] input1 = {1, 2, 3, 4};
    ArrayExamples.reverseInPlace(input1);
    System.out.println(Arrays.toString(input1));
    assertArrayEquals(new int[] {4, 3, 2, 1}, input1);
  }
```
  
Non-failure inducing input:
```
@Test
  public void testReverseInPlace2() {
    int[] input1 = {3, 2, 3};
    ArrayExamples.reverseInPlace(input1);
    System.out.println(Arrays.toString(input1));
    assertArrayEquals(new int[] {3, 2, 3}, input1);
  }
```
Symptoms of running tests using JUnit with both of these inputs:
  
![image6](./Screen%20Shot%202023-01-27%20at%203.41.14%20PM.png)
  
Though both tests were run, only testReverseInPlace2() obtained a failure result.
  
The original buggy code: 
```
static void reverseInPlace(int[] arr) {

    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
    
}
```
  
The fixed non-buggy code:
```
static void reverseInPlace(int[] arr) {

    for(int i = 0; i < arr.length/2; i += 1) {
      int element = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = element;
    }
    
}           
```
To fix this code, I reversed the array using the same method as the original code; this method involves swapping elements from both ends until the entire array is copied in reverse order. The original code does this swapping for the entire length of the array, while my code only iterates through the first half of the array. I also made a variable to store the original element at each index, so that I could reassign the value at the other end of the array, represented by the index "arr.length - i - 1", to that original element. This fix addresses the issue because it preserves the elements in the first half of the array; the original code was swapping elements throughout the array, which resulted in already-copied elements being copied again and consequently, the loss of some original elements.
  
### Part 3
  
In lab in Week 2, I learned how to clone a repository in Github and commit and push changes to a file using the Desktop app. I am super new to using Github, so I thought this lab was a cool way of getting more familiar with git commands and Github itself.
