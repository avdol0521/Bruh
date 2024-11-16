## nuggets:
- check the manual for extra in depth shit ig with man nmap
- how to log outputs: nmap (command and ip and all that bullshit) -oN (output.txt). or do -oA for compatibily with stuff like nessus and shit like that 
- do -Pn to disable pinging ig
- do -sV to show services 
	- example vuln services: vsftpd 2.3.4, openSSH upto 4.7.7 (for user enumeration) etc 
	- how to actually know what services are vulnerable: just google the port with the service number + "exploits" or check exploitDB
- stuff to look into:
	- ip table 
	- tcp headers
	- bin, push, arch
	- ttl value (used to guess target operating systems) (got by pinging and shit like that)
	- tmux
	- zombie ip
	- zombie scan 
	- zombie host
	- how to perform the zombie stuff (linked to the bangladesh bank hack in 2016)
- most of the commands ill need:
	1. -p
		- for port scanning
	2. -sC 
		- basic scan 
		- fpt-anon: allowed thakle anon login possible 
	3. -sV
		- show services
	4. -sT
		1. just checks the tcp ports. used after -sC
	5. -sU 
		1. just checks the udp ports. used after -sC as well 
	6. -sX
	7. -T
		1. aggression level
	8. -iL
		1. scans a list of sites/ips instead of a single one. syntax nmap -sV -iL (filename)
	9. -sL 
		1. similar to -iL but simple. use -iL instead coz the trainer said so
	10. --spoof-mac
		1. uses someone elses mac address to avoid getting fucked. nmap --spoof-mac dell
	11. -D
		1. decoy. use with stealth scan. nmap -sS -D (decoy ip or RND:number of random decoys u want)
	12. -sS
		1. stealth scan. used for firewall bypassing
	13. -A
	14. -oA
	15. -oN
	16. --script=(example like http or ssh)-*
		- explanation: chooses exactly which types of scripts to run. http or ssh is that type. and the -* says all the scripts of that type 
	17. 
## step 1: port checking
- check the ports
	- you can do -p- to check all the fucking ports or do -p443,88 and so on to check specific ports 
	- example ports: 80, 443, 5985, 3389, 139, 88, 21, 22, 5000, 5001, 8000, 8001
	- you can also do -p1-1000 to scan between 1 to 1000
- if the state is filtered then theres something going on with the ips or firewall
- what we want is the open ports and the services. then we can check if those services are vulnerable or not