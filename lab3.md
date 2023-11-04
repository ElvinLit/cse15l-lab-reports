# Lab Report 3

## Part 1 - Bugs
Choose one of the bugs from week 4’s lab.

Provide:
- A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
```java
@Test
public void testReversed2() {
  int[] input1 = {1,2,3,4,5};
  assertArrayEquals(new int[]{5,4,3,2,1}, ArrayExamples.reversed(input1));
}
```
This is the test case that I created which produced an error for the ArrayExamples.reversed() method. The expected list should be {5,4,3,2,1}, but {0,0,0,0,0} was returned instead. 

- An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
```java
 @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```
This is an input that doesn't induce a failure. It handles the case of an empty list. 
- The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)  
![Image](lab3_failures.png)  
In the symptom, it can be seen that the failed test case has a 0 in the first index when the expected is 5. The empty case works as intended.
- The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)  
Before:
```java
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
After:
```java
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
- Briefly describe why the fix addresses the issue.
The issue with the method was that instead of modifying the `newArray`, we were modifying the original `arr`. As a result, the method would always return a list of 0s since the elements that were being copied were values of 0 from the newly created empty array. To fix this, I simply changed the method to modify `newArray` so that it gets filled with elements from the original array. 

## Part 2 - Researching Commands
I am using the `find` command
1. `-type` option, which searches based on a specific type. 
  - Example 1) `find ./technical -type d`, which finds all directories within the directory `./technical`. This is useful if you want to filter out only the directories. 
    - Output:
```bash
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```
  - Example 2) `find ./technical -type f`, which finds all regular files within the directory `./technical`. This is useful if you want to filter out only the files. 
    - Output:
```bash
./technical/biomed/1471-2350-3-12.txt
./technical/biomed/1471-2350-3-7.txt
./technical/biomed/1471-2350-3-9.txt
./technical/biomed/1471-2350-4-2.txt
./technical/biomed/1471-2350-4-3.txt
./technical/biomed/1471-2350-4-4.txt
./technical/biomed/1471-2350-4-6.txt
./technical/biomed/1471-2369-3-1.txt
./technical/biomed/1471-2369-3-10.txt
...
```
