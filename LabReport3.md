# Bugs
Failure-inducing input for the `reversed` method in `ArrayExamples.java`:

```
@Test
  public void testReversed() {
    int[] input1 = {1};
    assertArrayEquals(new int[]{1}, ArrayExamples.reversed(input1));
  }
```

Input that does not create an error:

```
@Test
  public void testReversed2() {
    int[] input1 = {0};
    assertArrayEquals(new int[]{0}, ArrayExamples.reversed(input1));
  }
```

Symptom (Running Junit with the two tests above):

![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/f2d22de4-f706-45d8-9ec3-91e9eed72d7d)

Before/After code blocks to show the bug:
(before)
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

(after)
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

The bug in this method was that the method incorrectly copied values from `newArray` to `arr`, when it should have been the other way around. 
By copying from `newArray`, the buggy method would always return an array of zeroes, the default value for integers. The fixed version
copies from `arr` to `newArray` correctly.

# Researching Commands
Command chosen: `grep`

Use case 1:
`grep string file`
This searches for `string ` occurrences in the file given by `file`, printing out every line that has an occurrence.

