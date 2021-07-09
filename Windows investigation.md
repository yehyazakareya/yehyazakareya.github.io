
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


9- Then we have to investigate when did Jenny last logon so we will execute **net Users Jenny** 

![Jen.png]({{site.baseurl}}/Jen.png)


The answer is **Never** as shown above.

10- We have to check the Event viewer (security logs) to know when did the compromise take place , After checking we will see that it started at **03/02/2019**


11- By also checking the security logs we will know that windows first assign special privileges to a new logon was at **03/02/2019 4:04:49 PM** 


![security.png]({{site.baseurl}}/security.png)


12- Now we will check the path we saw before to investigate the incident **C:/TMP** so we notice that tool the hacker used to get Windows passwords is **Mimikatz**

![mimikatz.png]({{site.baseurl}}/mimikatz.png)


13- After checking the files in this path , this incident appear to be DNS cache poisoning attack so we can check DNS cache to know what is wrong by executing **Get-DnsClientCache**


![DNS.png]({{site.baseurl}}/DNS.png)


Now we notice something strange that www.google.com mapps to the IP **76.32.97.132** so it has to be the attackers external and command servers IP or we can check the host file in the following path **C:\Windows\System32\Drivers\etc**

![hosts.png]({{site.baseurl}}/hosts.png)


We will see the same thing at (www.google.com & google.com).



14- After that we have to know the extension of the shell uploaded via the servers website so we will check the path **C:\inetPub\wwwroot** and we will see that the shell is **.jsp** file


![Shell.png]({{site.baseurl}}/Shell.png)


15- To know the last port the attacker opened we have to check the firewall, Inbound Rules

![Firewall.png]({{site.baseurl}}/Firewall.png)


We know now it was port **1337** as shown above.


16-As it's mentioned above it is DNS poisoning atack and the site was targeted is **google.com** as shown.


![hosts.png]({{site.baseurl}}/hosts.png)