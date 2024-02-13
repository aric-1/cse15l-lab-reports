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

Source used for all use cases: https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix

Use case 1:

`grep -r string *`

This searches for `string` occurrences recursively in the current directory and subdirectories. This can be useful if you have a lot of files to search through and do not want to use `grep` for every file.

```
$ grep -r "among us" *
biomed/1471-2261-3-5.txt:        clinically diagnosed valve disease among users of
government/Post_Rate_Comm/ReportToCongress2002WEB.txt:unreasonable discrimination among users of the mails, nor shall it
```

```
$ grep -r "NBA" *
biomed/1471-2121-3-2.txt:        GENBANK database. The sequences for monkey LTBP-3 and
government/Gen_Account_Office/d01186g.txt:EXCEPTIONBASED SYSTEMS
```

Use case 2: 

`grep -i string file`

This searches for `string` occurrences in the file given without checking the case of alphabetic characters. This can be useful in searching for all occurrences of words, when you do not care about capitalization but also must find every occurrence.

```
$ grep -i "among" 911report/chapter-1.txt
    For those heading to an airport, weather conditions could not have been better for a safe and pleasant journey. Among the travelers were Mohamed Atta and Abdul Aziz al Omari, who arrived at the airport in Portland, Maine.
    The cockpit voice recorder captured the sounds of the passenger assault muffled by the intervening cockpit door. Some family members who listened to the recording report that they can hear the voice of a loved one among the din. We cannot identify whose voices can be heard. But the assault was sustained.
    Among the sources that reflect other important events of that morning, there is no documentary evidence for this call, but the relevant sources are incomplete. Others nearby who were taking notes, such as the Vice President's chief of staff, Scooter Libby, who sat next to him, and Mrs. Cheney, did not note a call between the President and Vice President immediately after the Vice President entered the conference room.
```

```
$ grep -i "Nairobi" 911report/chapter-2.txt
                in Nairobi as a cover for operatives there.)
            Al Qaeda leaders set up a Nairobi cell and used it to send weapons and trainers to
                begun casing targets in Nairobi for future attacks. It was led by Ali Mohamed, a
                in an apartment in Nairobi where the various al Qaeda operatives and leaders based
                embassy in Nairobi was an easy target because a car bomb could be parked close by,
                in Nairobi, and that Hage's telephone was being tapped. Hage was a U.S.citizen who
                being pulled together in Nairobi and Dar es Salaam. The timing and content of their
            The next four months were spent setting up the teams in Nairobi and Dar es Salaam.
                assist in putting the weapons together. In Nairobi, a hotel room was rented to put
                run at the embassy in Nairobi. By the evening of August 6, all but the delivery
                five minutes apart-about 10:35 A.M. in Nairobi and 10:39 A.M. in Dar es Salaam.
            The attack on the U.S. embassy in Nairobi destroyed the embassy and killed 12
```

Use case 3:

`grep -c string file`

This counts the number of lines in the file that contain the specified string. This is useful because it gives a rough idea of how much a certain word or phrase is used in a file.
```
$ grep -c Among 911report/chapter-1.txt
2
```

```
$ grep -c e 911report/chapter-2.txt
845grep 
```

Use case 4:

`grep -v string file`

This searches for `string ` occurrences in the file given by `file`, printing out every line that does not have an occurrence. This can be useful for filtering out tags in files where each line has a tag, or when you are very tired of seeing a certain string and would only like to read lines that do not contain it.

These examples also uses -c as the output would otherwise be very lengthy.
```
$ grep -v -c the 911report/chapter-1.txt
418
```

```
$ grep -v -c e 911report/chapter-2.txt
103
```

