<h1>Azure Sentinel and VM Honeypot Project</h1>

 

<h2>Description</h2>
This home lab project consist of creating an Azure virtual machine and setting it up as a honeypot to see how often the machine would be brute-forced by the public. I created an allow all rule in the firewall to make it discoverable to the public internet and turned off Windows Firewall on the VM. I created a log analytic workspace and connected it to the VM. I setup Azure Sentinel and connected it to the log analytic workspace. I enabled gathering VM logs in Microsoft Defender for the Cloud. I used a powershell script to run in background of the VM and collect the data from all host trying to brute force it. I was able to see their IP addresses, geolocation and the usernames that were used to try to gain access to the VM. I sent the collected data to a saved file on the VM and created a custom log in the log analytic workspace workbook to bring in the logs from the saved file. I ran a query in Sentinal to pull failed logon attempts in the log and created a map to show where the attacks were coming from.
<br />



<h2>Home Lab Details and Pics:</h2>

<p align="center">
Microsoft Sentinel Overview.  <br/>
<img src="https://i.imgur.com/bWHYL2V.png"
<br />
<br />
<br />
<br />
<br />
<p align="center">
Microsoft Sentinel Incident View. I created an alert rule for the failed logons. (Please excuse the misspelling of logons in the pic) <br/>
<img src="https://i.imgur.com/M0qef5j.png"
<br />
<br />
<br />
<br />
<br />
<p align="center">
World map of brute-force attacks: <br/>
<img src="https://i.imgur.com/vvzyLEb.png"
<br />
<br />
<br />
<br />
<br />
Powershell Script ran in VM and results. I got the script from Josh Madakor. The results were sent to a saved file on the VM and pulled into Azure: <br/>
<img src="https://i.imgur.com/C7xlB9i.png"
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
Event Viewer from the VM showing EventID: 4625 in the security logs. This EventID is an account failed to logon. These are saved on the VM and sent to Sentinel. <br/>
<img src="https://i.imgur.com/7xUyjNt.png"
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
