## Lab Report 3


# Part 1
Bug: Reversed Array
Code: Array Example
<br>
`public class ArrayExamples {`
`  // Changes the input array to be in reversed order ` <br>
`  static void reverseInPlace(int[] arr) {` <br>
`    for(int i = 0; i < arr.length; i += 1) {` <br>
`      arr[i] = arr[arr.length - i - 1]; ` <br>
`    }` <br>
`  }`

`  // Returns a *new* array with all the elements of the input array in reversed` <br>
`  // order` <br>
`  static int[] reversed(int[] arr) {` <br>
`    int[] newArray = new int[arr.length];` <br>
`    for(int i = 0; i < arr.length; i += 1) {` <br>
`      arr[i] = newArray[arr.length - i - 1];` <br>
`    }` <br>
`    return arr;` <br>
`  }`

`  // Averages the numbers in the array (takes the mean), but leaves out the` <br>
`  // lowest number when calculating. Returns 0 if there are no elements or just` <br>
`  // 1 element in the array` <br>
`  static double averageWithoutLowest(double[] arr) {` <br>
`    if(arr.length < 2) { return 0.0; }`<br>
`    double lowest = arr[0];`<br>
`    for(double num: arr) {`<br>
`      if(num < lowest) { lowest = num; }`<br>
`    }`<br>
`    double sum = 0;`<br>
`    for(double num: arr) {`<br>
`      if(num != lowest) { sum += num; }`<br>
`    }`<br>
`    return sum / (arr.length - 1);`<br>
`  }`<br>
`}`<br>

`  @Test`<br>
`  public void testReversed2() {`<br>
`    int[] input1 = { 1, 3, 2, 5 };`<br>
`    assertArrayEquals(new int[]{ 5, 2, 3, 1 }, ArrayExamples.reversed(input1));`<br>
`  }`

`  @Test`<br>
`  public void testReversed3() {`<br>
`    int[] input1 = { 1, 2, 3, 4, 5, 6 };`<br>
`    assertArrayEquals(new int[]{ 6, 5, 4, 3, 2, 1 }, ArrayExamples.reversed(input1));`<br>
`  }`

The Symptom: 
![Image](Lab4 Pic 1.png)

The Bug: <br>
` // Returns a *new* array with all the elements of the input array in reversed`<br>
` // order`<br>
`  static int[] reversed(int[] arr) {`<br>
`    int[] newArray = new int[arr.length];`<br>
`    for(int i = 0; i < arr.length; i += 1) {`<br>
`      arr[i] = newArray[arr.length - i - 1];`<br>
`    }`<br>
`    return arr;`<br>
`  }`
<br>
The fixed solution: <br>
`// Returns a *new* array with all the elements of the input array in reversed`<br>
`// order`<br>
`  static int[] reversed(int[] arr) {`<br>
`    int[] newArray = new int[arr.length];`<br>
`    for(int i = 0; i < arr.length; i += 1) {`<br>
`      newArray[i] = arr[arr.length - i - 1];`<br>
`    }`<br>
`    return newArray;`<br>
`  }`<br>

  The correct output:
  ![Image](Lab4 Pic 2.png)
# Part 2

Less <br>
https://en.wikipedia.org/wiki/Less_(Unix)#:~:text=less%20is%20a%20terminal%20pager,backward%20navigation%20through%20the%20file.
<br>
Searches and displays a file 1 screen at a time
<br>
-i
<br>
Similar to ctrl f on google, it is a case-insensitive search
<br>
![Image](Lab5 i2.png)<br>
launching the command<br>
![Image](Lab5 i.png)<br>
using the search feature to find all regardless of case<br>

-m
<br>
provides more details, such as file position 
<br>
![image](Lab5 m2.png)<br>
Launching the command<br>
![image](Lab5 m.png)<br>


-S
<br>
prevents lines from being tabbed automatically when exceeding the character limit. 
<br>
![image](Lab5 s2.png)<br>
Launching the command<br>
![image](Lab5 s.png)<br>
This file is tabbed manually so it doesn't overflow past the screen<br>
![image](Lab5 s1.png)<br>
This is to show that you can scroll sideways<br>

-N
<br>
Gives line numbers
<br>
![image](Lab5 n2.png)<br>
Launching the command<br>
![image](Lab5 n.png)<br>
This file now has the line number on the side.



