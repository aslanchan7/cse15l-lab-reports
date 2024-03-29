# Lab Report 3

## Part 1 - Bugs

**Failure Inducing Input**

```
@Test
public void testReversed2() {
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

![Image](lab-report-3-ss5.png)

Description: As you can see, there seems to be a failure for a test called `testReversed2()` which is the failure-inducing test shown above.

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

1. `-name`
2. `-type`
3. `-iname`
4. `-empty`

**`-name` Examples**

```
Aslan Chan@LAPTOP-HR2BVR3V MINGW64 ~/Classes/CSE 15L/Lab 5/docsearch (main)
$ find ./technical -name "911*"
./technical/911report
```

```
$ find ./technical -name "1468*"
./technical/biomed/1468-6708-3-1.txt
./technical/biomed/1468-6708-3-10.txt
./technical/biomed/1468-6708-3-3.txt
./technical/biomed/1468-6708-3-4.txt
./technical/biomed/1468-6708-3-7.txt
```

Description: The `-name` option allows a user to find files where the base of the file name matches the pattern that they provide. This may be useful if a user is trying to find a file that starts in a certain pattern/way.

**`-type` Examples**

```
Aslan Chan@LAPTOP-HR2BVR3V MINGW64 ~/Classes/CSE 15L/Lab 5/docsearch (main)
$ find ./technical -type f
./technical/911report/chapter-1.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
...
./technical/plos/pmed.0020275.txt
./technical/plos/pmed.0020278.txt
./technical/plos/pmed.0020281.txt
```

```
Aslan Chan@LAPTOP-HR2BVR3V MINGW64 ~/Classes/CSE 15L/Lab 5/docsearch (main)
$ find ./technical -type d
./technical
./technical/911report
...
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```

Description: The `-type` option finds files/directories that match the given type (eg: files, directories, characters). This is super helpful for finding all files of a certain type in a large directory.

**`-iname` Examples**

```
Aslan Chan@LAPTOP-HR2BVR3V MINGW64 ~/Classes/CSE 15L/Lab 5/docsearch (main)
$ find ./technical/government/ -iname "a*"
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen/atx1-6.txt
...
```

```
Aslan Chan@LAPTOP-HR2BVR3V MINGW64 ~/Classes/CSE 15L/Lab 5/docsearch (main)
$ find ./technical/biomed/ -iname "*x*.txt"
./technical/biomed/1471-213X-1-1.txt
./technical/biomed/1471-213X-1-10.txt
./technical/biomed/1471-213X-1-11.txt
./technical/biomed/1471-213X-1-12.txt
```

Description: The `-iname` option works exactly like `-name` except the name given is not case sensitive. This can be helpful to a user for finding a file whose name they do not know exactly.

**`-empty` Examples**

```
Aslan Chan@LAPTOP-HR2BVR3V MINGW64 ~/Classes/CSE 15L/Lab 5/docsearch (main)
$ find ./technical -empty
```

```
Aslan Chan@LAPTOP-HR2BVR3V MINGW64 ~/Classes/CSE 15L/Lab 5/docsearch (main)
$ find ./technical -empty
./technical/empty_directory
```

Description: The `-empty` option allows a user to find directories or files that are empty. This may be helpful to a user for when they want to clean up their project files and remove any ununnecessary files/directories.

