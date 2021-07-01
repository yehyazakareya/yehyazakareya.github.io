<span style=" font-size:37px;"> **Tools used:** </span><br/>

John The Ripper , ssh2john.py , GPG


<span style=" font-size:37px;"> **Walkthrough:** </span><br/>

1- The first task teaches us about the importance of encryption and how the client and the server establish a safe connection.

When you conncet to SSH, the client and the server establish an encrypted tunnel so no one can snoop on your session , the server has a certificate that uses cryptography to prove its identity and when you download a file , you can use cryptography to verify a checksum of the data to make sure that the file was downloaded in a right way.

Standards like PCI-DSS state that data should be encrypted both in storage and while being transmitted. These standards is used when handling payment card details.

2- The second task includes a little bit of math that comes up in cryptography like the mudlo operator which means the reminder of devision.

Ex: 118613842 % 9091

So first 118613842 / 9091  = 134047.39215

Then we will subtract the whole number as follows:

134047.39215-134047 = 0.39215

Then we will multiply this fractional part with 9091

0.39215 * 9091 = 3565 (this is the reminder)


3- The third task is about the types of encrytion.

1- Symmetric encryption : uses the same key to 
encrypt data like DES (56 bits long keys ) , it wasn't secure so they used another algorthim called triple DES to make it more secure. Another one is AES (128 or 256 bit long keys).

2-Asymmetric encryption : uses a pair of keys , public and private keys, one for encryption and the other for decrytion like RSA (2048 to 4096 bit keys).


4-The fourth task  explains how the client agree  a key with the server without transmitting the key.


5- The fifth task is explaining the concept of digital signatures and certificates.

You can know which company the website issued certificate to by clicking on the lock symbol in your browser

![lock.png]({{site.baseurl}}/lock.png)


6- In this part we will use JohnTheRipper tool and the wordlist rockyou to obtain the passphrase for the key.

First we will convert the idrsa.id_rsa into a hash file by using ssh2john.py tool and we will save the output in the directory to use JohnTheRipper to crack it so we will execute the following command

**python ssh2john idrsa.id_rsa >> ~/src/john/run/id.hash**

![hash.png]({{site.baseurl}}/hash.png)


Then we will you the wordlist (rockyou.txt) to crack the password by executing

**./john --wordlist=rockyou.txt id.hash**

![src.png]({{site.baseurl}}/src.png)


![password.png]({{site.baseurl}}/password.png)


So the password is delicious.


7- The seventh part explains Diffie Hellman key exchange 

If two devices want to communicate safely over the network, they have to use a secret key, Diffie Hellman key exchange is the way how this secret key is made and it's almost impossible to be known by the public.

8-In this part we will use GPG and the private key given (tryhackme.key) to decrypt the file and know the secret word

First we will import the secret key using the command

**gpg --import /path/to/the/secret key**


![key.png]({{site.baseurl}}/key.png)


Then we will decrypt using the gpg file using the following command 

**gpg -d /path/to/the/encrypted message** 

note:**-d** flag is used to decrypt the message

![gpg.png]({{site.baseurl}}/gpg.png)


The secret word is pineapple.

7- The final part is talking about the relation between quantum computers and encryption and why quantum computers are dangerous to some encryption algorithms 