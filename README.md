<h1>Azure Sentinel and VM Honeypot Project</h1>

 

<h2>Description</h2>
This home lab project consist of creating an Azure virtual machine as a honeypot to see how often the machine would be brute-forced by the public. I created an allow all rule in the firewall to make it discoverable to the public internet and turned off Windows Firewall on the VM. I created a log analytic workspace and connected it to the VM. I setup Azure Sentinel and connected it to the log analytic workspace. I enabled gathering VM logs in Microsoft Defender for the Cloud. I used a powershell script to run in background of the VM and collect the data from all host trying to brute force it. I was able to see their IP addresses, Geolocation and the usernames they used to try to gain access to the VM. I sent the collected data to a saved file on the VM and created a custom log in the log analytic workspace workbook to bring in the logs from the saved file. I ran a query in Sentinal to check for failed logon attempts in the log and setup a map to show where the attacks were coming from.
<br />



<h2>Home Lab Details and Pics:</h2>

<p align="center">
Microsoft Sentinel <br/>
<img src=
<br />
<br />
<p align="center">
World map of brute-force attacks: <br/>
<img src=
<br />
<br />
Powershell Script ran in VM and results. The results were sent to a saved file on the VM: <br/>
<img src=
<br />
<br />
Query ran in Sentinel and results. You can see the attackers IP address and the usernames used during the attack:  <br/>
<img src=
<br />
<br />
Query: <br/>
<img src=
<br />
<br />
Query:  <br/>
<img src=
<br />
<br />
Alerts:  <br/>
<img src=
<br />
<br />
Playbooks:  <br/>
<img src=
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
