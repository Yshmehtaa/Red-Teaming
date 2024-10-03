https://github.com/jonaslejon/malicious-pdf

If you Admin creds -- download RSAT and Access Active directory users and group 

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
