# Lab Report 5

## Step 1:

Student's Post:

Hello, I'm having a problem with my randomSort algorithm. When I run the bash script to test it, nothing happens; I expect the code to print some output. I am completely lost.

![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/1c70ff1d-cb06-41fb-a3bf-fe5dcf9008ff)

![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/70dc0760-3e5f-4f68-b799-0b8d459794dd)

Here's a screenshot of my code so far:

![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/5df5970e-83b0-49db-9231-a70858b4cd95)

## Step 2:

TA's Response:

It looks like your program isn't terminating. There is probably an infinite loop somewhere in your code. Have you checked that the while loop's termination condition is correct? You should try setting a breakpoint in VSCode and debugging it using the step button.

## Step 3:

Student:

I found the bug in the program! You were right that it was an infinite loop, and that the problem was with the while loop's termination condition. I accidentally initialized the boolean variable `sorted` to `false` so that it could never be true. 
This means the program never exited the loop or returned anything, which is why my terminal got stuck.

Picture of VSCode Java debugger working:

![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/082299a8-c09d-4a25-a302-ea2f29827506)


## Setup Information

File Structure:

![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/e02cd19b-e8ff-40cc-9dfe-e16983469e96)

Contents of the files before the bug fix:

![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/1c70ff1d-cb06-41fb-a3bf-fe5dcf9008ff)

![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/27ea6976-3cf7-4697-bac7-ff98f2ee952a)


Command line run to trigger the bug:

`bash Test.sh`

How to fix the bug:

In line 23 of `MyRandomSort.java` , change `boolean sorted = false;` to `boolean sorted = true;`

## Reflection

  Something I learned from the labs the second half of the quarter is how to use Vim. I had tried to use it before when my older brother
  who also went to UCSD made me use it to edit files, but he was not a good teacher and I did not understand what was going on at all.
  I found out that the program itself is actually pretty cool, even if it does have incredibly unintuitive commands and no intuitive way to exit
  the editor or save your file. I also think the vim tutor is very cool and an excellent example of what a tutorial should be.
