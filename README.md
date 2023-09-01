<h1>Microsoft Sentinel and VM Honeypot Project</h1>

 

<h2>Description</h2>
This home lab project consist of creating an Azure virtual machine and setting it up as a honeypot to see how often the machine would be brute-forced. I created an allow all rule in the firewall to make it discoverable to the public internet and turned off Windows Firewall on the VM. I created a log analytic workspace and connected it to the VM. I setup Azure Sentinel and connected it to the log analytic workspace. I enabled gathering VM logs in Microsoft Defender for the Cloud. I used a powershell script to run in background of the VM to collect failed logon attempts from Event Viewer. I'm able to see IP addresses, geolocation data and the usernames used during attacks. The collected data is saved in a file on the VM and pulled into the log analytic workspace. I ran a query in Sentinal to pull failed logon attempts in the log and created a map to show where the attacks were coming from.
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
World map of brute-force attacks locations. This map was created in workbook using the geolocation data pulled from the Powershell Script. 
<br />
<br />
<br />
<br />
<br />
<br/>
<img src="https://i.imgur.com/C7xlB9i.png" <br />
Powershell Script ran on the VM and results. The PowerShell script extracts metadata from Windows Event Viewer and forwards it to a third party API to get geolacation data from attacks. I made an account on ipgeolocation.io to receive an API key. The API key needs to be added to the PowerShell script so you can get geolocation. The events are saved in a file on the VM and sent to Azure. Event Viewer shows EventID 4625. This ID indicates an account failed to logon.
<br />
<br />
<img src="https://i.imgur.com/7xUyjNt.png"
<br />
<br />
<br />
<br />
<br />
Query ran in Sentinel and results. You can see the attackers IP address, location, and the usernames used during the attack:  <br/>
<img src="https://i.imgur.com/OqlKLR1.png"
<br />
<br />
<br />
<br />
<br />
This pic shows I assigned the incident to myself. 
<img src="https://i.imgur.com/PqoHVGW.png"
<br />
<br />

 <!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
