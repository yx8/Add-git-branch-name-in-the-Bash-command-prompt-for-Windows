# Add-git-branch-name-in-the-Bash-command-prompt-for-Windows
Tutorial on adding git branch name in the Bash command prompt for Windows

# If you are working with Git in Windows and you want to show the git branch name in the Bash command prompt. Here is the solution to do it. 


First of all, it's good to use a Linux like Bash command prompt tool in Windows, here I will use the Cygwin as an example, you can use most of the Linux/ Mac OS command in this tool.

- We can downsload Cygwin from their official website
  [https://cygwin.com/install.html](https://cygwin.com/install.html) 

- After installation go to this directory.
 
 
```sh
C:\cygwin64\home\[your system username]
```

![1](https://github.com/yx8/Add-git-branch-name-in-the-Bash-command-prompt-for-Windows/blob/master/img/1.png?raw=true)

- Then we open up this file `.bashrc` with a text editor.

- Scroll Down to the bottom of those codes inside.  
- Copy and paste these two line of codes below on the bottom of the codes inside the `.bashrc` file.

```sh


parse_git_branch() { git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/' ; }
export PS1="\u@\h \[\033[32m\]\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "


```


![2](https://github.com/yx8/Add-git-branch-name-in-the-Bash-command-prompt-for-Windows/blob/master/img/2.png?raw=true)

- Save and close. 



That's it, now when you are accessing the Github directory on Windows in the Bash command prompt it will show the Git branch name just like it displays in Linux/ Mac OS. With the `Master` or the branch names in brackets.

![3](https://github.com/yx8/Add-git-branch-name-in-the-Bash-command-prompt-for-Windows/blob/master/img/3.png?raw=true)

Simply done and a very useful feature when you are developing on a Windows system.

Hope you find it easy and straight forward to do it. :)




