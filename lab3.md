# Lab Report 3
## Part 1
---

This is the failure-inducing JUnit test:
```
@Test
    public void testReversedFailure() {
        int[] inputArray = {1, 2, 3, 4, 5};
        int[] expectedArray = {5, 4, 3, 2, 1};
        assertArrayEquals(expectedArray, ArrayExamples.reversed(inputArray));
    }
```

This is the JUnit test that passes:
```
@Test
    public void testReversedSuccess() {
        int[] inputArray = {1, 2, 3, 4, 5};
        int[] expectedArray = {0, 0, 0, 0, 0}; // This is what the original buggy code would return
        assertArrayEquals(expectedArray, ArrayExamples.reversed(inputArray));
    }
```

Screenshots of the outputs from running the tests:

Failed-

![Image](Lab 3 Failed Test Output.PNG)


Passed-

![Image](Lab 3 Success Output.PNG)

The bug I chose from week 4's lab is from ArrayExamples.java, specifically the reversed method, which is below

---
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
The issue here is in the for loop:
```
arr[i] = newArray[arr.length - i - 1];
```
The statement initializes "newArray" as an array of zeros and assigns this to arr[i]. This bug causes arr always to be written as an array of zeros instead of reversing.

This is the fixed code below
```
static int[] reversedFixed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
The fixed code contains the corrected statement:
```
newArray[i] = arr[arr.length - i - 1];
```
This assigns the value of `arr[arr.length - i - 1]`, the reversed array, to newArray which is then returned.

## Part 2
---

