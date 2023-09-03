<h1>Microsoft Sentinel and VM Honeypot Project</h1>

 

<h2>Description</h2>
This home lab project consist of setting up Microsoft Sentinel and an Azure Virtual Machine. I set the VM as a honeypot to see live attacks and how often the machine would be brute-forced. I created an allow all rule in the firewall to make it discoverable to the public internet and turned off Windows Firewall on the VM. I connected the VM to my log analytic workspace. I used a PowerShell script to run in background of the VM to collect failed logon attempts. I'm able to see IP addresses, geolocation data and the usernames used during attacks. The collected data is saved in a file on the VM and pulled into the log analytic workspace. I ran a query in Sentinal to pull failed logon attempts in the log and created a map to show where the attacks were coming from.
<br />



<h2>Home Lab Details and Pics:</h2>

<p align="center">
<br/>
<img src="https://i.imgur.com/bWHYL2V.png" <br />
Microsoft Sentinel Dashboard Overview
<br />
<br />
<br />
<br />
<br />
<p align="center">
<br/>
<img src="https://i.imgur.com/M0qef5j.png" <br />
Microsoft Sentinel Incident View. I created an alert rule for the failed logons. (Please excuse the misspelling of logons in the pic) 
<br />
<br />
<br />
<br />
<br />
<p align="center">
<br/>
<img src="https://i.imgur.com/vvzyLEb.png" <br />
<img src="https://i.imgur.com/V5DYu9C.png" <br />
World maps of brute-force attack locations. These maps was created in workbook using the geolocation data pulled from the Powershell Script. 
<br />
<br />
<br />
<br />
<br />
<img src="https://i.imgur.com/sgM3HeJ.png" <br />
<br />
Bar chart of attack locations. The Netherlands leading the attacks at the time the chart was created. <bf />
<br />
<br />
<br />
<br />
<br />
<img src="https://i.imgur.com/C7xlB9i.png"
<br />
<br />
<img src="https://i.imgur.com/7xUyjNt.png" <br />
<br />
Powershell script ran on the VM and results. The PowerShell script extracts metadata from Windows Event Viewer and forwards it to a third party API to get geolacation data from attacks. I made an account on ipgeolocation.io to receive an API key. The API key needs to be added to the PowerShell script so you can get geolocation. The events are saved in a file on the VM and sent to Azure. Event Viewer shows EventID 4625. This ID indicates an account failed to logon.
<br />
<br />
<br />
<br />
<br />
<img src="https://i.imgur.com/OqlKLR1.png" <br />
<img src="https://i.imgur.com/5WAke6O.png" <br />
Query ran in Sentinel and results. You can see the attackers IP address, location, and the usernames used during the attack
<br />
<br />
<br />
<br />
<br />
<img src="https://i.imgur.com/el7m89z.png" <br />
I created a rule to create an incident on Failed RDP Logons.
<br />
<br />
<br />
<br />
<br />
<img src="https://i.imgur.com/PqoHVGW.png" <br />
<br />
This pic shows me assigning the incident to myself. You will do this working as a Security Analyst in a SOC before investigating them.
<br />
<br />
