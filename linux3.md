<span style=" font-size:37px;"> **Commands used:** </span><br/>

ssh , nano , wget , python3 -m http.server , ps aux ,  systemctl  ,fg , crontab -e , cat , apt


<span style=" font-size:37px;"> **Walkthrough:** </span><br/>


1- The first task is to connect to the linux machine so we will use the command **ssh tryhackme@machine_IP**


2- The second task learns us how to use text editors such as: nano or vim . We can create a new file using nano by executing **nano file**.

Now we have to look for the flag so firstly we will open (task3) file using nano as follows **nano task3** , and here we found the flag: THM{TEXT_EDITORS}

![nano.png]({{site.baseurl}}/nano.png)


3- The third task requires from us to run a web server on our machine so we will use this command **python3 -m http.server** and we will open a new terminal window and we will download a file from this server on port 8000 and the name of this file is (.flag.txt) so we will execute **wget http://MACHINE_IP:8000/.flag.txt** to download the file

![python3.png]({{site.baseurl}}/python3.png)


![wget.png]({{site.baseurl}}/wget.png)

Then we will try to dispaly the contents of the file so we will use **ls** , something weird is happening the file isn't listed among the other files so it looks like a hidden file so we will use **ls -a** to list all the files and we will use the command **cat .flag.txt** to output the content of the file, bingo the flag is: THM{WGET_WEBSERVER}

![hide.png]({{site.baseurl}}/hide.png)


4- The fourth task teaches us about the processes, we are asked to locate the process running on the machine_IP so we will execute the following command to list all the processes of all users running on the machine **ps aux** and we will look for something suspicious. Here we find the flag: THM{PROCESSES}

![proccess.png]({{site.baseurl}}/proccess.png)


In order to stop the service (myservice) from running we use **systemctl stop myservice** and if we want to start the same service when the system boots up we use **systemctl enable myservice** 


Note: if we want to background a process we can use ctrl+Z , and if we want to foreground a backgrounded process we use **fg** command.

5- The fifth task teaches us about the crontabs which is used to schedule a certain task every certain amount of time.

We can use nano to edit crontabs using **crontab -e** , the crontab deploy on this machine at reboot.

![crontab.png]({{site.baseurl}}/crontab.png)


6- The sixth task is talking about the package managment , repositories and how to add a new one using **add-apt-repository** after downloading the GPG key using **wget** and use **apt-key** to trust it.

7- The seventh task teaches us how to navigate through logs, in this challenge we suppose to look for apache2 logs , find IP address of the user visited the site and the file they access , so firstly we will change the current directory to **/var/log/apache2** and look for apache2 logs

![var.png]({{site.baseurl}}/var.png)


Then we will use **cat access.log.1** to see who accessed this file recently and the file they accessed.

![apache.png]({{site.baseurl}}/apache.png)

