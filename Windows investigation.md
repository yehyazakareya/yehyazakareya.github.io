
<span style=" font-size:37px;"> **Description:** </span><br/>

A windows machine have been hacked, its your to go investigate this windows machine and find clues to what the hacker might have done.


<span style=" font-size:37px;"> **Walkthrough:** </span><br/>

1- The first task is to know the version and the year of the windows machine , so we will execute this command **system info** 

![info.png]({{site.baseurl}}/info.png)


2- The second task is to know which user logged on last so by checking the security logs we will find out that it is the **Administrator**

3-To know when did john log onto the system last we will execute **net Users john**

![john.png]({{site.baseurl}}/john.png)


So as shown the last logon was **3/2/2019 5:48:32 PM**


4-When the machine starts up we will notice something strange, that a process is executed remotely and it's trying to connect to IP **10.34.2.3** and it's located and the following path **C:\TMP\p.exe**



![IP.png]({{site.baseurl}}/IP.png)



5-Now we need to know the users that had administrative privileges so we will check the computer managment tool and the see the local users the groups , So now we now that **Jenny** & **Guest** that had administrative privileges because they are members of Administrators group

![Groups.png]({{site.baseurl}}/Groups.png)


6-Now we are supposed to investigate the name of the malicous scheduled task so we will check the Task schedular tool and look for the malicous task , When we check the **Clean file system** task we will find something weird , that is starts a program in the same path we saw before C:/TMP so it has to be the malicous task

![clean.png]({{site.baseurl}}/clean.png)


![clean2.png]({{site.baseurl}}/clean2.png)


7,8- And it was trying to run the powershell file **nc.ps1** and the file was listening locally for port **1348** as shown above 

