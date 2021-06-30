<span style=" font-size:37px;"> **Tools used:** </span><br/>

Ping , Traceroute , Whois , Dig 


<span style=" font-size:37px;"> **Walkthrough:** </span><br/>

1- The first part is an introduction about OSI 7 layer model and how each works and handles the data.

The first layer (physical) transmitts and receives data then the second layer (Data link) checks the received packets which is called (Frames) to make sure that they haven't been corrupted by adding trailer at the end of the transmission and present data in a suitable format for transmission then the third layer (Network) handles logical addressing then the fourth layer (Transport) choose to send data over TCP, the data is called (segments) by establishing stable connection between the two computers which is called three-way handshake (SYN , SYN/ACK ,ACK)or UDP, it's called (Datagrams) then the fifth layer (session) tracks communications between the host and receiving computers then the sixth layer (Presentation) encrypts or transforms initial data to give it a standardised format and finally the seventh layer (Application) accepts communcation requests from applications.

The process of sending data from one computer to another is called encapsulation and the process that the receiving computer perform on the massage is called de-encapulation. These processes are used to add extra layer of security. 

Note: the FTP protocol communicate with the seventh layer (Application)



2- The second part compares between TCP/IP model and OSI 7 layer model.

-The network interface layer in TCP/IP model is equivalent to the physical and data link layers in OSI model.

-The internet layer in TCP/IP model is equivalent to the Network layer in OSI model.

-The transport layer is the same at both models

-The Application layer in TCP/IP model is equivalent to the session , presentation and application layers in the OSI model.


Note: TCP is called connection-based protocol whie UDP is called contionless protocol.


3- We will use ping tool on the bbc.co.uk website by executing **ping bbc.co.uk** and we can use **-c** flag to specify number of request we want to send

![pping.png]({{site.baseurl}}/pping.png)


Now we want to use ping to know the ipv4 address of  this website (muirlandoracle.co.uk) so we will use the following command **ping muirlandoracle.co.uk -4** , **-4** flag is used to specify the IPV4 address of the website

![ping2.png]({{site.baseurl}}/ping2.png)


Note: **-i** flag is used to change interval between sent requests and **-v** is used to give you more verbose output , you can use manual pages to find more ping flages by executing **man ping** 


3 - we will use traaceroute tool on tryhackme.com website by executing   **traceroute tryhackme.com** and you can use **man traceroute** to find more about this command

Note: **-I** flag is used to specify interface when using traceroute and **-T** flag is used when we want to use TCP SYN requests when tracing route.


4- we will use the tool whois on facebook.com as follows **whois facebook.com** and we will start collecting some information about the website like creation date of the domain and the registrant postal code

![postal.png]({{site.baseurl}}/postal.png)


Then we will use the same tool on microsoft.com **whois microsoft** to collect some information like the city the registrant based in and the registrant Tech Email

![city.png]({{site.baseurl}}/city.png)


![email.png]({{site.baseurl}}/email.png)


Now we suppose to find the name of the golf course that is near registant address of microsoft.com so we will use the information we collected earlier about the registrant street and city: (one microsoft way)(Redmond) and search for it ,you can use yelp for example

![yelp.png]({{site.baseurl}}/yelp.png)


4- The fourth task teaches us about dig tool and DNS severs (domain name system).

