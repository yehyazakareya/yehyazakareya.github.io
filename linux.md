---
published: true
---
<span style=" font-size:37px;"> **Commands used:** </span><br/>
 echo , whoami , ls , cd , cat , pwd , grep .
 
 <span style=" font-size:37px;"> **walkthrough:**</span><br/>
1- The first task is to output the text "TryHackMe" so we will use the command **echo TryHackMe** 

 After that we suppose to find out the username of who you are logged in as so we will use the command **whoami** as shown:
![Whoami.png]({{site.baseurl}}/Whoami.png)

2- The second task teaches us  how to navigate the machine using commands such as:

**ls:**  lists the directories and files 

**cd:**  is used to change directory 

**pwd:** prints current directory 

**cat:** outputs the contents of a file

Now we will use the command **ls*** to know the number of folders on the machine , asterisk is 
a wild card that lists all folders contents at once 

![ls.png]({{site.baseurl}}/ls.png)

Then we will use the command **cat folder4/note.txt** to know the content of folder4

![cat.png]({{site.baseurl}}/cat.png)

After that we will change the current directory to follder4 using the command **cd folder4** and outputs the full path of the current directory using the command **pwd** as follows:

![pwd.png]({{site.baseurl}}/pwd.png)

IN order to search for a word or prefix  in a certain file we use the command grep + word + file name which looks like that **grep THM access.log** and after executing this command we found the flag : THM{ACCESS}

![grep.png]({{site.baseurl}}/grep.png)

3- The third task is to use shell operators to write to files so we will start by introducing some shell operators like:

**&:** allows you to run commands in background

**>:** redirector which takes output from command and directs it

**>>:** appends the output to certain file

After knowing a little bit about shell operators we will use that knowledge to create file named password and add the word (password123) to it using the command **echo password123 > passwords** then we will append another word (tryhackme) to the file passwords using the command **echo tryhackme >> passwords** as follows:

![echo1.png]({{site.baseurl}}/echo1.png)
![echo2.png]({{site.baseurl}}/echo2.png)
