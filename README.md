Install powershell on the system manually by pwsh.exe 
https://github.com/PowerShell/PowerShell/releases


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
