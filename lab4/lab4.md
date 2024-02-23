##Login to the Server

![Image](lab4/lab-report-4-ss1.png)

I typed `ssh asc010@ieng6.ucsd.edu` and pressed `<enter>`.

##Cloning the Forked Repo

![Image](lab4/lab-report-4-ss2.png)

I then typed `git clone ` followed by `<ctrl><v>` to paste the ssh url that I copied from github. I then pressed `<enter>` to execute the command.

##Running the Tests

![Image](lab4/lab-report-4-ss3.png)

Once I had cloned the repo, I typed `cd la <tab> <enter>`. This auto-completed the dir name for me and now I was in the `lab7` directory. I then typed `ls` to know what was in the directory. After that, I typed `bash te <tab> <enter>` to auto-complete the `test.sh` and run the tests. It showed that the tests failed, as expected.

##Fixing the Bugs

![Image](lab4/lab-report-4-ss4.png)

![Image](lab4/lab-report-4-ss5.png)

I then typed `vim List <tab> .java <enter>`. This opened the screen on the second screenshot shown above. Now, it was time to fix the bug. I typed `:$` to go to the end of the file, then I pressed `k` 7 times to move up to the line of the bug. After that, I typed `e` to go to the end of the first word which was `index1`. I then pressed `x` to remove the `1`, pressed `i` to enter INSERT mode, pressed `2` to insert 2 in the correct position, pressed `<esc>` to go back to normal mode, and finally `:wq` to save and exit.

##Re-Running the Tests

![Image](lab4/lab-report-4-ss6.png)

I then typed `bash te <tab>` again to re-run the tests and the tests passed this time.

#Committing and Pushing the Changes to GitHub

![Image](lab4/lab-report-4-ss7.png)

Now, I typed `git add .` to add all the changes that I have made in this directory. Then `git commit -m "Fixed bugs"` to commit my changes with the message "Fixed bugs", then `git push` to push the changes to GitHub.
