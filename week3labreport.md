## Week 3 Lab Report
**Sujana Sreenivasan**

### Part 1

Here are some screenshots for a program I wrote called StringServer.java. The goal of this program is to act as a web server that keeps track of a single string that gets added to by incoming requests, in the form of a path that looks like "/add-message?s=<string>".

  
The first screenshot shows the code itself and how the program is implemented. The next screenshots show two different tester methods that call the program's primary methods to test the code using JUnit. 
 
The first tester screenshot calls the addString() method in order to send a new path request to the running string. This test first passes in the argument "/add-message?s=Hello" to addString(), then calls it a second time while passing in the argument "/add-message?s=How are you". As can be seen from the first screenshot, the main data field in the StringServer class is runningString, which is initialized as an empty string and stores the updated string as new path requests come in and are processed. This field is updated with each call to addString(); for this test, runningString is first updated to "\nHello", and after the second method call, gets changed to "\nHello\nHow are you".
  
The second tester operates essentially the same way as the first; it calls addString() three times, passing in arguments of "/add-message?s=Good afternoon!", "/add-message?s=Today is Friday.", and "/add-message?s=:)" for each time respectively. The test also calls getString() to get the updated runningString after each requested string is added to it. After the first method call to addString(), runningString is changed to "\nGood afternoon!". After the second call to addString(), runningString changes to "\nGood afternoon!\nToday is Friday.". Following the third call, the final value of runningString for this tester is "\nGood afternoon!\nToday is Friday.\n:)".
  
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
Symptoms of running tests with both of these inputs:
  
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
    int[] placeholder = new int[arr.length];
    for (int i = 0; i < arr.length; i++) {
      placeholder[i] = arr[i];
    }

    for(int i = 0; i < arr.length/2; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
    for(int i = arr.length/2; i < arr.length; i += 1) {
      arr[i] = placeholder[arr.length - i - 1];
    }
    
  }            
```
This fix addresses the issue because I initially made a copy of the input array and stored it in the placeholder array. Then I wrote two for loops that iterate through the first half and second half of the input array, respectively. I copy the items from the original array in the first loop, and copy items from the placeholder array in the second loop, which ultimately preserves the order of elements when reversing the array. The original code reverses the original array, which means it is copying elements into the array that have already been copied, rather than using the original elements.
  
### Part 3
  
In lab in Week 2, I learned how to clone a repository in Github and commit and push changes to a file using the Desktop app. I am super new to using Github, so I thought this lab was a cool way of getting more familiar with git commands and Github itself.
