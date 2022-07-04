# ANNIE 
1.  first step is the resonance so I did the Nmap  the command i used was 
	
		nmap -sC -sV  $IP
	so i get the result like 
	
		port 22 ssh
		port 7070 unknown
	the port 7070 feels awkward so i did a scan specially for port 7070

		nmap -sC -sV -p7070 $IP
	and got the results like 

	it was anydesk port so i did some Searchsploit and came up with

		searchsploit anydesk 
	the result was ![[rick.jpg]]

	and i use the one with the remote code execution

2. 