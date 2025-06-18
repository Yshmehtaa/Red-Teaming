
Install powershell on the system manually by pwsh.exe (even if the PS is blocked from the domain)
https://github.com/PowerShell/PowerShell/releases

https://chatgpt.com/share/68496748-7470-8012-8166-308af12d8503


for explots use the following websites 
1. cvedetails.com 
2. exploitdb.com 
3. rapid7.com 
4. 0day.today 

To check the IP address of the web-application which is behind the firewall 
1. ping the domain 
2. Tracert the site
3. nslookup 
4. verify if the website is really giving the firewall IP 
5. securityTrails and search domain 
6. censys.io 
7. shodan.io


https://github.com/jonaslejon/malicious-pdf

If you Admin creds -- download RSAT and Access Active directory users and group 
https://www.microsoft.com/en-us/download/details.aspx?id=45520
Get-WindowsCapability -Name RSAT* -Online | Add-WindowsCapability -Online 

Look for the RSAT is present in the System -- > settings -> Optionals features 

To assign the IP in the windows look for the Network apdapter 
Control Panel\Network and Internet\Network Connections 
Select network adapter Ethernet -> right click -> properties -> Internet Protocol version 4 (TCP/IPv4) 
Enter the IP 

ACcess the share folder through Windows 
1. Open run (ctrl + r) \\IP
2. File explorer \\IP


Access share folder through kali 
smbclient and smbmap 
1. smbclient -H IP
2. smbmap -H IP -d domain -u ad_id -p ad_pass
3. 




##Chatgpt prompts for redteaming 
Can I run PowerShell remotely from Kali against the Windows machine?
Can I simulate the PowerShell environment of Windows by running it on Kali?
Can I bypass the local PowerShell restriction by using PowerShell from Kali?
how to Download PowerShell portable version on the Windows machine


Command to list the Domain Controllers 
nltest/dclist:DOMAIN


command to forcefully update the latest GPO Policy to update is 
gpudate /force 

While capturing the response from the Responder - 
the captured NTLMv2-SSP Hash/Net-NTML hash- 
The format of this hash look like this 

Challenge.Signature.MD5 

while authenticating or using the hashes always use the --local-auth because it will  login as the local administrator. 

If we are not not using --local-auth we trying to login as domain account/domain user if at all the hash is not proper then we can lock out the administrator account 

also use --lsa after you recognize the local administrator  


This all will be blocked by the EDR; so you can do is install the RAMDUMP (where the password used are stored in the RAM) and Analys the ramdump using the tool volatility tool. (used for the forensics)  

Manual approach to enumerate the Domain - cmd,powershell 

net users/user  /domain 
net user "" /domain 
net group /domain 
net group "" /domain 
net account /domain 
nltest /dclist:domainname (list the domain controllers: PDC(primary domain controller))

PS> Powerview - commands 
Get-NetComputer | select dnshostname  (All the computers in the domain)
Get-NetComputer -Ping | select dnshostname  (All the computer which are reachable in the domain) 
Get-NetUser | select samaccountname, description 
Get-NetUser
Get-NetUser "user" 


