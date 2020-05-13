# Target - UltraTech
	ip: 10.10.223.88

# Recon
## nmap
	nmapFastScan ip
		21/tcp   open     ftp             vsftpd 3.0.3
		22/tcp   open     ssh             OpenSSH 7.6p1 Ubuntu 4ubuntu0.3
		1086/tcp filtered cplscrambler-lg
		8081/tcp open     http            Node.js Express framework

## dirsearch
	dirsearch ip:8081
		[13:27:52] 200 -   39B  - /auth/
		[13:27:52] 200 -   39B  - /Auth/
		[13:27:52] 200 -   39B  - /auth
		[13:28:14] 500 -    1KB - /ping
