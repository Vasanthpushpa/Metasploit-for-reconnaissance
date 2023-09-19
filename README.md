# Metasploit-for-reconnaissance

# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

## PROGRAM:
Find out the ip address of the attackers system

## OUTPUT:
![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/24b9e11d-12f6-4c84-b69d-8d1bba43267e)

### Invoke msfconsole:
![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/74829b0b-192b-4d47-ba14-b6ac6d76e218)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:
![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/e8d04084-852a-47b9-b42b-072ccb979cc9)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/d3f755ab-62ee-494d-9483-808903859ba7)

## Step4: 
Use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.
scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/a12c96aa-8cc8-44e6-a4d0-bc52cfa557f3)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:
![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/5d01132a-d516-430d-b598-8ed8486fa8e7)

![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/d4bd13ff-a006-43ec-9ef9-2140cf8abe16)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/5301a7a0-54e4-4c98-904d-6f8916726153)

The info command provides information regarding a module or platform

## OUTPUT:
![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/1e9f4c07-aa49-4b5b-988f-3c2bfb4901aa)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/69b80746-c175-4a11-b75c-67d44b77586e)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/0e280ace-da60-41a5-a03f-669d5c6b397e)

Use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/69e8f46a-fc76-4675-992b-58ea7ed8ec2b)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/9d363f70-7514-444c-856f-22d6cbce4e88)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/SivaramakrishnanBaskar/Metasploit-for-reconnaissance/assets/119476322/543e68f9-e16b-4045-ad6b-760e3a753ac5)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
