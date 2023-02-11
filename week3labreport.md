## Week 3 Lab Report
**Sujana Sreenivasan**

### Part 1

Here are some screenshots for a program I wrote called StringServer.java. The goal of this program is to act as a web server that keeps track of a single string that gets added to by incoming requests, in the form of a path that looks like "/add-message?s=(string)".

![image1](./Screen%20Shot%202023-01-26%20at%207.34.26%20PM.png) 
  
The first screenshot shows the code itself and how the program is implemented. It utilizes the pre-created file Server.java to properly handle the URL and launch the server. The next screenshots show the web server in action by testing it using URLs from the browser. 

![image2](./Screen%20Shot%202023-01-26%20at%207.45.41%20PM.png)
![image3](./Screen%20Shot%202023-01-26%20at%207.33.13%20PM.png)
  
The first tester screenshot obtains the above output by calling the addString() method in order to send a new path request to the running string. This test first passes in the argument "/add-message?s=Hello" to addString(), then calls it a second time while passing in the argument "/add-message?s=How are you". As can be seen from the first screenshot, the main data field in the StringServer class is runningString, which is initialized as an empty string and stores the updated string as new path requests come in and are processed. This field is updated with each call to addString(); for this test, runningString is first updated to "\nHello", and after the second method call, gets changed to "\nHello\nHow are you", which is the output printed in the terminal.

![image4](./Screen%20Shot%202023-01-26%20at%207.45.58%20PM.png)
![image5](./Screen%20Shot%202023-01-26%20at%207.33.37%20PM.png)
  
The second tester operates essentially the same way as the first in order to get the above output; it calls addString() three times, passing in arguments of "/add-message?s=Good afternoon!", "/add-message?s=Today is Friday.", and "/add-message?s=:)" for each time respectively. The test also calls getString() to get the updated runningString after each requested string is added to it. After the first method call to addString(), runningString is changed to "\nGood afternoon!". After the second call to addString(), runningString changes to "\nGood afternoon!\nToday is Friday.". Following the third call, the final value of runningString for this tester is "\nGood afternoon!\nToday is Friday.\n:)". This same output is printed in the terminal.
  
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
