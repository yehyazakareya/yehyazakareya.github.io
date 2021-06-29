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


4- The fourth task is



