<h1> Scanning for Vulnerabilities with Tenable Nessus Agent (Linux) </h1>

 ###

<h2> Lab Description & Objectives </h2>
In this lab, I will demonstrate how to deploy a Tenable Nessus Agent on a Linux virtual machine, connect it to the Tenable Cloud platform, and perform an agent-based vulnerability assessment. The objective is to identify security vulnerabilities on a Linux endpoint without relying on traditional network scans....
<br />


<h2> Skills Demonstrated </h2>

- <b> Linux Administration
- SSH Remote Access
- Vulnerability Management
- Tenable Nessus
- Agent-Based Security Monitoring
- Cloud Security
- Bash
- Cybersecurity Documentation
- Troubleshooting </b> 
- <b>Diskpart</b>

<h2>Environments Used </h2>

- <b>Linux Virtual Machine
- Tenable.io / Tenable Cloud
- Nessus Agent
- SSH
- Bash
- Virtual Machine</b> (21H2)

<h2>Step 1 — Provision a Linux Virtual Machine</h2>

<p align="center">
Launch the utility: <br/>

<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
