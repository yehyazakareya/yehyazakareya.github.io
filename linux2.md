<span style=" font-size:37px;"> **Commands used:** </span><br/>
ssh , man ,  touch , file , mv , cat , ls , su

<span style=" font-size:37px;"> **Walkthrough:** </span><br/>


1- The first task was to use **ssh** command to login to the remote machine so we will execute the following command **ssh tryhackme@machine Ip**

2- The second task was to use the manual pages to  explore  the command ls the command looks like that **man ls**

![man.png]({{site.baseurl}}/man.png)

note: -h flag is used to display the output in human readable way

then we suppose to create a file named (newnote)  we will use **touch newnote** command as follows:

![touch.png]({{site.baseurl}}/touch.png)

Now we have to know the file tye of (unknown1), in order to accomplish this task we will execute the this command **file unknown1**

![file.png]({{site.baseurl}}/file.png)

After that we want to move the file named (myfile) to the directory (myfolder) so we will use this command **mv myfle myfolder**

![move.png]({{site.baseurl}}/move.png)

Finaaly we must discover the contents of (myfile) so we will use **cat myfile** command

![cat2.png]({{site.baseurl}}/cat2.png)

3- The third task
