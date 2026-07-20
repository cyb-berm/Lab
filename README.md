# 🔍 Scanning for Vulnerabilities with Tenable Nessus Agent (Linux)

---

## 📖 Overview

This project demonstrates how to deploy a **Tenable Nessus Agent** on a Linux virtual machine, connect it to the Tenable Cloud platform, and perform an **agent-based vulnerability assessment**.

The objective of this lab is to gain hands-on experience deploying endpoint security software, initiating vulnerability scans, analyzing findings, and understanding how organizations continuously monitor systems for security risks.

---

# 🎯 Objectives

- Provision a Linux Virtual Machine
- Configure a Nessus Agent Group
- Deploy a Nessus Agent
- Connect the endpoint to Tenable Cloud
- Trigger a vulnerability scan
- Analyze scan results
- Document findings
- Remove lab resources

---

# 🛠 Skills Demonstrated

- Linux Administration
- SSH Remote Access
- Vulnerability Management
- Endpoint Security
- Cloud Security
- Bash
- Security Monitoring
- Risk Assessment
- Cybersecurity Documentation
- Troubleshooting

---

# 💻 Technologies Used

- Ubuntu Linux
- Tenable.io
- Nessus Agent
- SSH
- Bash
- Virtual Machine

---

# 🖥 Lab Environment

| Component | Description |
|------------|-------------|
| Operating System | Ubuntu Linux |
| Scanner | Nessus Agent |
| Platform | Tenable Cloud |
| Access Method | SSH |
| Shell | Bash |

---

# 🚀 Step 1 – Provision a Linux Virtual Machine

## Objective

Create a Linux virtual machine that will serve as the endpoint for vulnerability scanning.

## What I Did

I provisioned a Linux VM and created a secure administrator account using a strong password rather than the default credentials.

This ensures the endpoint is properly secured before connecting it to the Tenable platform.

<img width="1512" height="788" alt="1" src="https://github.com/user-attachments/assets/ec0bfc97-9d77-4b65-8a6d-036c43cc6772" />

### Key Takeaway

Using strong credentials is a basic but essential security control.

---

# 🚀 Step 2 – Create a Nessus Agent Group

## Objective

Create an Agent Group to organize managed endpoints.

## What I Did

Within the Tenable Cloud portal, I created a new Nessus Agent Group.

The agent group allows multiple endpoints to be centrally managed and scanned together.


<img width="1512" height="828" alt="Screenshot 2026-07-19 at 11 18 36 AM" src="https://github.com/user-attachments/assets/e6645bbe-7142-4067-bd7c-3f33df899bbc" />


### Key Takeaway

Agent Groups simplify vulnerability management across multiple systems.

---

# 🚀 Step 3 – Configure a Triggered Scan

## Objective

Create a scan that can be manually triggered from the endpoint.

## What I Did

I configured a **Triggered Basic Agent Scan** and associated it with the newly created Agent Group.

I also selected a trigger filename that would later initiate the scan "start.txt".

<img width="1512" height="822" alt="Screenshot 2026-07-19 at 11 37 05 AM" src="https://github.com/user-attachments/assets/716bbf12-490f-4c3e-9cf9-ff7d5b37de90" />


### Key Takeaway

Triggered scans allow the endpoint itself to initiate vulnerability assessments.

---

# 🚀 Step 4 – Connect to the Linux VM

## Objective

Access the Linux endpoint remotely.

## What I Did

I connected to the Linux virtual machine using SSH.

### Command Used

```bash
ssh username@IP-ADDRESS
```

<img width="1903" height="957" alt="Screenshot 2026-07-19 at 3 32 38 PM" src="https://github.com/user-attachments/assets/5070d08f-39d6-4581-84f9-f3802c04adb9" />


### Key Takeaway

SSH provides secure encrypted remote administration of Linux systems.

---

# 🚀 Step 5 – Generate the Nessus Agent Installation Command

## Objective

Generate an installation command that registers the endpoint with Tenable Cloud.

## What I Did

Inside Tenable Cloud, I created a new Nessus Agent installation command and customized it with my Agent Group information.


<img width="1908" height="959" alt="Screenshot 2026-07-19 at 3 53 48 PM" src="https://github.com/user-attachments/assets/1368d8c2-c7f3-4847-bf1d-6d6b9359e78b" />


### Key Takeaway

The registration key securely links the endpoint to the Tenable Cloud platform.

---

# 🚀 Step 6 – Install the Nessus Agent

## Objective

Install and register the Nessus Agent.

## What I Did

I elevated to root privileges and executed the installation command.

### Commands Used

```bash
sudo -i
```

```bash
curl -H 'X-Key: XXXXXXX' https://sensor.cloud.tenable.com/install/... | bash
```


<img width="1902" height="957" alt="Screenshot 2026-07-19 at 3 59 02 PM" src="https://github.com/user-attachments/assets/83d6f2b6-9368-4ad8-bf2d-002ff6bb82bf" />


### Key Takeaway

The endpoint is now managed through Tenable Cloud.

---

# 🚀 Step 7 – Trigger the Vulnerability Scan

## Objective

Initiate the agent scan.

## What I Did

I manually created the trigger file used by the Nessus Agent.

### Command Used

```bash
touch /opt/nessus_agent/var/nessus/triggers/start.txt
```

### Screenshot

<img width="967" height="143" alt="Screenshot 2026-07-19 at 4 02 52 PM" src="https://github.com/user-attachments/assets/92ba907d-180c-46a3-a1c4-661ef2864a47" />


### Key Takeaway

Creating the trigger file instructs the agent to begin scanning.

---

# 🚀 Step 8 – Verify the Scan Started

## Objective

Verify that the agent accepted the trigger.

## What I Did

I monitored the trigger directory until the trigger file disappeared.

### Commands Used

```bash
cd /opt/nessus_agent/var/nessus/triggers
```

```bash
ls -lasht
```

<img width="770" height="265" alt="Screenshot 2026-07-19 at 4 28 31 PM" src="https://github.com/user-attachments/assets/afca2234-a4a4-4021-99ea-b1a3a5a773e9" />


### Key Takeaway

Once the trigger file disappears, the Nessus Agent has started the vulnerability scan.

---

# 🚀 Step 9 – Verify the Agent in Tenable Cloud

## Objective

Confirm successful registration.

## What I Did

I navigated to the Nessus Agents page and verified my endpoint appeared online.

### Screenshot

<img width="1565" height="38" alt="Screenshot 2026-07-19 at 4 40 59 PM" src="https://github.com/user-attachments/assets/d171e142-eac3-494a-9bc9-b03fb42f2176" />


### Verification

- Agent Name
- Online Status
- Registration Date
- Agent Group

---

# 🚀 Step 10 – Analyze Vulnerability Results

## Objective

Review vulnerabilities discovered by the Nessus scan.

## What I Did

After the scan completed, I reviewed the vulnerability report and analyzed the discovered findings.


<img width="1860" height="899" alt="Screenshot 2026-07-19 at 4 45 53 PM" src="https://github.com/user-attachments/assets/2414077d-5d7c-4725-ad63-3eb3d612f1ab" />


### Information Reviewed

- Severity Levels
- CVEs
- CVSS Scores
- Vulnerability Descriptions
- Recommended Remediation

### Key Takeaway

Understanding vulnerability severity helps prioritize remediation efforts.

---

# 🚀 Step 11 – Monitor the Scan

## Objective

Observe the Nessus Agent process.

## What I Did

I monitored the Linux system using the `top` command.

### Command Used

```bash
top
```

### Key Takeaway

Monitoring system processes helps verify the scan is actively running.

---

# 🚀 Step 12 – Cleanup

## What I Did

After completing the lab, I cleaned up all cloud resources.

- Deleted the scan
- Deleted the Agent Group
- Unlinked the Nessus Agent
- Deleted the Linux VM

This prevents unnecessary cloud resources from remaining active.

---

- Verified the installation
- Restarted the Nessus Agent
- Waited for synchronization
- Confirmed the endpoint successfully registered

---

# 🔒 Security Concepts Learned

- Vulnerability Management
- Agent-Based Scanning
- Endpoint Security
- Continuous Monitoring
- CVEs
- CVSS Scoring
- Risk Prioritization

---

# 📚 Lessons Learned

During this lab, I learned how endpoint-based vulnerability scanning differs from traditional network scanning.

I also gained hands-on experience installing and configuring a Nessus Agent, connecting it to Tenable Cloud, triggering scans manually, and analyzing vulnerability data.

This project improved my Linux command-line skills and reinforced the importance of continuous vulnerability management in enterprise environments.

---

# 🚀 Future Improvements

- Deploy multiple endpoints
- Compare authenticated vs. unauthenticated scans
- Integrate results with a SIEM
- Automate deployment using Ansible
- Practice vulnerability remediation and rescanning

---

# 📌 Skills Demonstrated 

- Vulnerability Management
- Linux Administration
- Bash
- SSH
- Endpoint Security
- Tenable Nessus
- Cloud Security
- Security Monitoring
- CVE Analysis
- Risk Assessment
- Troubleshooting
- Technical Documentation

---
