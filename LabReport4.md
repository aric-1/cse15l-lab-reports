# Lab Report 4: Vim

## Step 4
Keys pressed:

`ssh ars027@ieng6.uscd.edu<enter>`
![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/32c82e91-a89b-4f15-a068-37f2f476ffe5)

With the `ssh` command, I entered into the ieng6 remote computer on my account. Since I already set up an ssh key, I
did not need to enter my password to login.

## Step 5
Keys pressed:

`git clone git@github.com:aric-1/lab7.git<enter>`
![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/c31cc3b9-ad91-4b37-a828-6dc7b7d1515f)

The clone command makes a copy of the directory given as an argument. Here, I used the ssh URL to clone the repository.

## Step 6
Keys pressed:

`cd lab7<enter>`
This command changes the directory to the lab7 directory so I can directly access the java files and shell files I need to run the tests.

`bash t<tab><enter>`
The bash command runs shell files. I used the tab shortcut to autocomplete the name of the shell file I want, `test.sh`. 

![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/2bbb3272-1fde-40e4-8932-4f386e4a3c2d)

## Step 7
Keys pressed:
`vim ListExamples.java 8j8j8j8j8jjjjexi2<esc>:wq<enter>`

First, I used Vim to open the file and navigated to the location of the error using the `j` shortcut that move the cursor down one line and numbers to indicate how many times to repeat it.
Then, I used the `e` shortcut to move to the end of the next word to get to the location of the error.
I used `x` to delete the erroneous character and `i` to enter insert mode. I then pressed 2 to replace the character and used `esc` and `:wq` to exit vim.

![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/888841fd-b422-4af3-93b9-594d63bffa87)


## Step 8

Keys pressed:

'<up><up><enter>'
By pressing the up arrow twice, I brought up the command `bash test.sh` (which I had run before the previous command) to run the tests. Then, I pressed enter to execute the tests.

![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/0562c7f0-9f88-4867-9bd8-0749cb091b6b)

## Step 9
Keys pressed:

`git add ListExamples.java<enter>`
This command adds the edited java file to the commit.

`git commit<enter>iDone!<esc>:wq<enter>`
This command commits the files with a message of `Done`, added using the insert shortcut `i` on the prompt that appears after the command runs.

`git push origin`
This command pushes the repository to GitHub.
![image](https://github.com/aric-1/cse15l-lab-reports/assets/156359530/434534d9-7667-4543-b1ce-4be0562c7d3e)



