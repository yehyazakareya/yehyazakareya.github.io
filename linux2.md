<span style=" font-size:37px;"> **Commands used:** </span><br/>
ssh , man ,  touch , file , mv , cat , ls , su

<span style=" font-size:37px;"> **Walkthrough:** </span><br/>


1- The first task is to use **ssh** command to login to the remote machine so we will execute the following command **ssh tryhackme@machine Ip**

2- The second task is to use the manual pages to  explore  the command ls, the command looks like that **man ls**

![man.png]({{site.baseurl}}/man.png)

note: -h flag is used to display the output in human readable way

then we suppose to create a file named (newnote)  we will use **touch newnote** command as follows:

![touch.png]({{site.baseurl}}/touch.png)

Now we have to know the file tye of (unknown1), in order to accomplish this task we will execute the this command **file unknown1**

![file.png]({{site.baseurl}}/file.png)

After that we want to move the file named (myfile) to the directory (myfolder) so we will use this command **mv myfle myfolder**

![move.png]({{site.baseurl}}/move.png)

Then we must discover the contents of (myfile) so we will use **cat myfile** command

![cat2.png]({{site.baseurl}}/cat2.png)

3- The third task is learning about the different users on the same machine so first we have to know the owner of the file (important) so we will execute the command **ls -l** ,    **-l** is used to list permissions,owners and groups of the files.

![-l .png]({{site.baseurl}}/-l .png)


Now we need to switch to user2 using the command **su user2**

![su.png]({{site.baseurl}}/su.png)

After that  we open the file (important) to know its content using **cat important** command and here  we find the flag: THM{SU_USER2}

![cat3.png]({{site.baseurl}}/cat3.png)

4- The fourth task is to know the most common directories such as:

**/etc:** it stores the sudoers , passwd , shadow files , they show how the system stores the password for each user in encrypted formatting (sha512)

**/var:** stores frequently accessed data by services or apps like log files

**/root:** it's like the home directory for root user

**/tmp:** stores data that is needed to be accesssed once or twice and user can write to this folder by default which can be used to store scripts.
