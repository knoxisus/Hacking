#Target - Vulnversity
ip: 10.10.52.250

#Recon
##nmap
nmapFastScan ip:
	21/tcp   open  ftp         vsftpd 3.0.3
	22/tcp   open  ssh         OpenSSH 7.2p2 Ubuntu
	139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X
	445/tcp  open  netbios-ssn Samba smbd 4.3.11-Ubuntu
	3128/tcp open  http-proxy  Squid http proxy 3.5.12
	3333/tcp open  http        Apache httpd 2.4.18 ((Ubuntu))

##dirsearch
dirsearch ip:3333
	[13:23:12] 301 -  318B  - /js  ->  http://10.10.106.132:3333/js/
	[13:23:42] 301 -  319B  - /css  ->  http://10.10.106.132:3333/css/
	[13:23:46] 301 -  321B  - /fonts  ->  http://10.10.106.132:3333/fonts/
	[13:23:49] 301 -  322B  - /images  ->  http://10.10.106.132:3333/images/
	[13:23:50] 200 -   32KB - /index.html
	[13:23:50] 301 -  324B  - /internal  ->  http://10.10.106.132:3333/internal/

#Explotation
#Netcat
ncx 4444

##Webshell php
	Extension .php bloqueada
	Intruder --> fuzz extension "/SecLists/Fuzzing/extensions-most-common.fuzz.txt"
	extension alowed: .phtml
	ir a "/internal/uploads/" y dar click al archivo que se subio

	nc fire!!!!

##Excalation:
	ir a /home
		user: bill
		flag: 8bd7992fbe8a6ad22a63361004cfcedb

	Finding files base on their permisions: find / -perm -4000 --> /bin/systemctl
	
		user: root
		flag: xxxx

	

