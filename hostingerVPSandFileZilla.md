# Setting up hostinger VPS ( Ubuntu 22 ) and FileZilla
 
\[yash@fedora ~\]$ ssh-keygen -R 147.162.228.118 

\# Host 147.162.228.118 found: line 1

/home/yash/.ssh/known_hosts updated.

Original contents retained as /home/yash/.ssh/known_hosts.old

 
\[yash@fedora ~\]$ ssh-keygen -R 147.162.228.118 

Cannot stat /home/yash/.ssh/known_hosts: No such file or directory

 
\[yash@fedora ~\]$ ssh root@147.162.228.118

The authenticity of host '147.162.228.118 (147.162.228.118)' can't be established.

RSA key fingerprint is SHA256:88jyPq4Y8ESQZqD4qLZjqQG7sSXiM05zYMtVqhibrEg.

This key is not known by any other names

Are you sure you want to continue connecting (yes/no/\[fingerprint\])? yes

Warning: Permanently added '147.162.228.118' (RSA) to the list of known hosts.

root@147.162.228.118's password: 
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

**Welcome to One-Click OpenLiteSpeed Node.js Server.**

To keep this Droplet secure, the firewalld is enabled.

All ports are BLOCKED except 22 (SSH), 80 (HTTP) and 443 (HTTPS).

The Node.js OLS One-Click Quickstart guide:

\* **https://docs.litespeedtech.com/cloud/images/nodejs/**

In a web browser, you can view:

\* The sample node site: http://147.162.228.118/

On the server:

\* You can get the Web Admin admin password with the following command:
   sudo cat .litespeed_password

System Status:

  Load : 0.00, 0.01, 0.01
  
  CPU  : 0.110122%
  
  RAM  : 52/1024MB (5.08%)
  
  Disk : 1/20GB (7%)

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

**To visit your apps by domain instead of IP, please enter a valid domain.**

**If you don't have one yet, you may cancel this process by pressing CTRL+C and continuing to SSH.**

**This prompt will open again the next time you log in, and will continue to do so until you finish the setup.**

**Make sure the domain's DNS record has been properly pointed to this server.**

Enter the root domain only, then the system will add both the root domain and the www domain for you.

Your domain: ^Z


Please input a valid domain


root@yashp2411:~# cd /

root@yashp2411:/# adduser yash

Adding user `yash' ...

Adding new group `yash' (1000) ...

Adding new user \`yash' (1000) with group \`yash' ...

Creating home directory `/home/yash' ...

Copying files from `/etc/skel' ...

New password: 

Retype new password: 

passwd: password updated successfully

Changing the user information for yash

Enter the new value, or press ENTER for the default

	Full Name \[\]: 
	
	Room Number \[\]: 
	
	Work Phone \[\]: 
	
	Home Phone \[\]: 
	
	Other \[\]: 

Is the information correct? \[Y/n\] 

root@yashp2411:/# 

root@yashp2411:/# usermod -aG sudo yash

root@yashp2411:/# ufw status

Status: inactive

root@yashp2411:/# ufw allow OpenSSH

ERROR: problem running

root@yashp2411:/# ufw app list

Available applications:

  Apache
  
  Apache Full
  
  Apache Secure
  
  Bind9
  
  OpenSSH

root@yashp2411:/# ufw enable

Command may disrupt existing ssh connections. Proceed with operation (y|n)? y

Firewall is active and enabled on system startup

root@yashp2411:/# ufw status

Status: active

To                         Action      From

\-\-                         \-\-\-\-\-\-      \-\-\-\-

22                         ALLOW       Anywhere                  

80                         ALLOW       Anywhere                  

443                        ALLOW       Anywhere                  

OpenSSH                    ALLOW       Anywhere                  

22 (v6)                    ALLOW       Anywhere (v6)             

80 (v6)                    ALLOW       Anywhere (v6)             

443 (v6)                   ALLOW       Anywhere (v6)             


root@yashp2411:/# exit

logout

Connection to 147.162.228.118 closed.

 
\[yash@fedora ~\]$ ssh yash@147.162.228.118

yash@147.162.228.118's password: 

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

**Welcome to One-Click OpenLiteSpeed Node.js Server.**

To keep this Droplet secure, the firewalld is enabled.

All ports are BLOCKED except 22 (SSH), 80 (HTTP) and 443 (HTTPS).

The Node.js OLS One-Click Quickstart guide:

\* **https://docs.litespeedtech.com/cloud/images/nodejs/**

In a web browser, you can view:

\* The sample node site: http://147.162.228.118/

On the server:

\* You can get the Web Admin admin password with the following command:

  sudo cat .litespeed_password

System Status:

  Load : 0.00, 0.01, 0.01
  
  CPU  : 0.121299%
  
  RAM  : 52/1024MB (5.08%)
  
  Disk : 1/20GB (7%)


\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

To run a command as administrator (user "root"), use "sudo &lt;command&gt;".

See "man sudo_root" for details.

\[sudo\] password for yash: 

**To visit your apps by domain instead of IP, please enter a valid domain.**

**If you don't have one yet, you may cancel this process by pressing CTRL+C and continuing to SSH.**

**This prompt will open again the next time you log in, and will continue to do so until you finish the setup.**

**Make sure the domain's DNS record has been properly pointed to this server.**

Enter the root domain only, then the system will add both the root domain and the www domain for you.

Your domain: ^Z

Please input a valid domain

**yash@yashp2411**:**~**$ exit

logout

Connection to 147.162.228.118 closed.

 
\[yash@fedora ~\]$ ssh-keygen

Generating public/private rsa key pair.

Enter file in which to save the key (/home/yash/.ssh/id_rsa): 

Enter passphrase (empty for no passphrase): 

Enter same passphrase again: 

Your identification has been saved in /home/yash/.ssh/id_rsa

Your public key has been saved in /home/yash/.ssh/id_rsa.pub

The key fingerprint is:

SHA256:eGzQkZhRFJBNHyueoOi9t/JlVxd7oz/7x1OghOoacEU yash@fedora

The key's randomart image is:

+---\[RSA 3072\]----+
|  .=.o.oE.       |
|  . o.==..       |
|  . .o+ o  . .   |
|.. o o.=  . . +  |
|o   + o S. o + + |
|. .  o o. . o o o|
| . .  .\+ .   . ..|
|   ...o.o     .oo|
|   .+oo.       oB|
+----\[SHA256\]-----+

 
\[yash@fedora ~\]$ 

 
\[yash@fedora ~\]$ ssh-copy-id root@147.162.228.118 

/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed

/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys

root@147.162.228.118's password: 

Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'root@147.162.228.118'"

and check to make sure that only the key(s) you wanted were added.


 
\[yash@fedora ~\]$ ssh root@147.162.228.118

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

**Welcome to One-Click OpenLiteSpeed Node.js Server.**

To keep this Droplet secure, the firewalld is enabled.

All ports are BLOCKED except 22 (SSH), 80 (HTTP) and 443 (HTTPS).

The Node.js OLS One-Click Quickstart guide:

\* **https://docs.litespeedtech.com/cloud/images/nodejs/**

In a web browser, you can view:

\* The sample node site: http://147.162.228.118/

On the server:

\* You can get the Web Admin admin password with the following command:

  sudo cat .litespeed_password

System Status:

  Load : 0.14, 0.05, 0.02
  
  CPU  : 0.122607%
  
  RAM  : 52/1024MB (5.08%)
  
  Disk : 1/20GB (7%)

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

Last login: Thu Mar 23 21:15:49 2023 from 43.251.92.113

**To visit your apps by domain instead of IP, please enter a valid domain.**

**If you don't have one yet, you may cancel this process by pressing CTRL+C and continuing to SSH.**

**This prompt will open again the next time you log in, and will continue to do so until you finish the setup.**

**Make sure the domain's DNS record has been properly pointed to this server.**

Enter the root domain only, then the system will add both the root domain and the www domain for you.

Your domain: ^Z

Please input a valid domain

root@yashp2411:~# exit

logout

Connection to 147.162.228.118 closed.

 
\[yash@fedora ~\]$ echo unable to connect to FileZilla

unable to connect to FileZilla

 
\[yash@fedora ~\]$ ssh root@147.162.228.118

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

**Welcome to One-Click OpenLiteSpeed Node.js Server.**

To keep this Droplet secure, the firewalld is enabled.

All ports are BLOCKED except 22 (SSH), 80 (HTTP) and 443 (HTTPS).

The Node.js OLS One-Click Quickstart guide:

\* **https://docs.litespeedtech.com/cloud/images/nodejs/**

In a web browser, you can view:

\* The sample node site: http://147.162.228.118/

On the server:

\* You can get the Web Admin admin password with the following command:

sudo cat .litespeed_password

System Status:

  Load : 0.00, 0.02, 0.02
  CPU  : 0.124051%
  RAM  : 52/1024MB (5.08%)
  Disk : 1/20GB (7%)

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

Last login: Thu Mar 23 21:35:49 2023 from 43.251.92.113

**To visit your apps by domain instead of IP, please enter a valid domain.**

**If you don't have one yet, you may cancel this process by pressing CTRL+C and continuing to SSH.**

**This prompt will open again the next time you log in, and will continue to do so until you finish the setup.**

**Make sure the domain's DNS record has been properly pointed to this server.**

Enter the root domain only, then the system will add both the root domain and the www domain for you.

Your domain: ^Z

Please input a valid domain


root@yashp2411:~# grep Subsystem /etc/ssh/sshd_config

**Subsystem**	sftp	/usr/libexec/openssh/sftp-server

root@yashp2411:~# for i in $(grep Subsystem /etc/ssh/sshd\_config | awk '{print $3}'); do sed -i 's|'"$i"'|internal-sftp|g' /etc/ssh/sshd\_config; done

root@yashp2411:~# service sshd reload

root@yashp2411:~# exit 

logout

Connection to 147.162.228.118 closed.

 
\[yash@fedora ~\]$ echo connected to FileZilla Successfully

connected to FileZilla Successfully

 
\[yash@fedora ~\]$




