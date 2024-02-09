![image](https://github.com/aslanchan7/cse15l-lab-reports/assets/124756060/a85a239a-56e9-4012-a86e-c91c5a921602)# Lab Report 3

## Part 1 - Bugs

**Failure Inducing Input**

```
@Test
public void testReversed() {
  int[] input1 = { 1, 2, 3 };
  assertArrayEquals(new int[] { 3, 2, 1 }, ArrayExamples.reversed(input1));
}
```

**Non-Failure Inducing Input**

```
@Test
public void testReversed() {
  int[] input1 = {};
  assertArrayEquals(new int[] {}, ArrayExamples.reversed(input1));
}
```

**Screenshots of the Symptoms**

![Image](lab-report-3-ss1.png)

![Image](lab-report-3-ss2.png)

**Before & After Bug Fix**

**Before**

```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for (int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```

**After**

```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for (int i = 0; i < arr.length; i += 1) {
    newArray[i] = arr[arr.length - 1 - i];
  }
  return newArray;
}
```

Description: The `reversed()` method before was assigning the elements from `newArray` to `arr`. Since `newArray` is an array with null elements, the `arr` stores null and hence does not reverse the array contents and causes a bug. The new `reversed()` method assigns `newArray` from `arr` in the opposite order and works as intended.

## Part 2 - Researching Commands

**Find Command**

**Options**

1. -name
2. -type
3. -iname
4. -regex


