Windows issue in using Linux 
=============================

**Problem-1:** Not confortable in using the command prompt of windows and want a similar terminal that in Linux.

**Solution:**

Install GitBash in windows. It provide terminal to access in the folder in windows using bash command that we commonly use in Linux. 

-----------------

**Problem-2:** Not able to open python in GitBash.

**Solution:** 

Create a ~/.bash-profile in windows if doesnot exist and add the following entry at the top of the file.
```
alias python='winpty python.exe'
```
[Detailed Answer Link](https://stackoverflow.com/questions/32186840/git-for-windows-doesnt-execute-my-bashrc-file/32189255#32189255)
