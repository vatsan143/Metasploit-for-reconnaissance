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

## PROGRAM:
Find out the ip address of the attackers system


## OUTPUT:

![272643902-8812a518-23f7-42dd-96e9-a273fa11b248](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/88b7f25d-ffec-4885-8f56-2f70e126e26e)

## Invoke msfconsole:
## OUTPUT:
![272643956-e545f5e3-9b74-41f7-92ea-5a777304d213](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/159be54a-99cb-4b13-bbbb-1f826334d978)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
![272644016-0d0d00e0-b8de-4857-8028-5d70319df6a2](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/01d26673-86f4-41d9-8979-41f155ba38c8)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![272644101-3bc823e8-55e2-4a0b-a209-fe1b08a566a5](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/eda0a522-70ba-4f57-a773-40860f66444e)

 ## Step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![272644170-6bdec805-cca7-468f-985b-35dc78d2f04c](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/5beb7b72-6d21-4a97-b4c6-f984b13de87e)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![272644230-bb190fc2-074c-457e-b306-9fb1d2073017](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/f6968c73-09b7-410c-a5cf-6c1a860994af)

![272644283-cdad6652-196e-44d9-8a36-a721f9ea0950](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/587d56aa-aabd-4ac3-9771-2ceb079e1385)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![272644346-4aa41d96-b79d-4b47-9908-2fedf278073c](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/c07fa026-b51c-4684-99a2-698bd63f28bc)

The info command provides information regarding a module or platform
## OUTPUT:

![272644394-616e5eec-f850-4276-b73e-6a9fbdc2a661](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/e5cc3c1c-8cd5-4dcf-b994-8b3410480510)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![272644449-c9b14466-35bc-4881-980a-3f95362e5130](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/292d3d3f-5740-4c2b-92f8-4dfd465a5a49)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![272644514-37478ecd-be0e-492b-aa49-33821f62b204](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/2477b07a-4904-41ca-b034-5a2aad460bbb)


use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version


![272644563-efe321cc-c1d1-4111-8188-89addb276bd0](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/8ada969f-b3ed-407e-9928-0859b52bfd83)

Use the set rhosts command to set the parameter and run the module, as follows:


![272644624-42bc034b-e464-4e11-8d3a-da5c2c5d4f83](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/cd8a7d5b-db4f-4ffd-866c-a47e2e5dc19d)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.


![272644682-db7a7f18-2620-4a7a-bc46-7d5782e54522](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/483721cb-b14b-4aa6-9334-39c5bfdeead5)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true


![272644745-f0dbd616-d1fc-4b0c-923b-bb112bdcf7b4](https://github.com/vatsan143/Metasploit-for-reconnaissance/assets/147368204/3b11366e-71ab-440a-a637-ffeb90e97255)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
