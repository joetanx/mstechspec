<details><summary>Prompt</summary>
i have gathered the following use cases for EDR and SOAR solution from the security team:

1. To create a blocking rule in firewall based on the IP address
- To be able to ingest a csv file attachment from email server through a specific template (i.e. removal of [.] from csv file)
- To make changes in firewall to block all outbound connection (An approval workflow is required before modification of firewall rules.) 

2. To show case the capability of implementing an automated response plan with zero-day vulnerability such as Log4J or known vulnerabilities/domain such as Polyfill:
- To collection of indicators suspected of trying to exploit the relevant CVEs or through email server
- To perform active search detection based on the reported signature
- The ability to perform virtual patching to reduce attack surface related to the zero day vulnerability


3. To demonstrate playbook on investigation of suspicious activities (e.g. misused account/high login failures):
- To detect or correlate alerts from log (i.e. Azure Log Analytics workspace/ AWS Cloudtrail) to detect login failure events and/or identify potential misuse of action:
- To show which processes/applications are using these accounts or how this activities are triggered
- To inform the incident response team to investigate via email
- To allow the team to disable the account, if required.

4. To be able to automatically perform threat hunting to detect anomaly (e.g. an application connecting to a malicious IP based):
- To be able to receive Threat Intelligence (TI) such as virus total, alienvault or OTX
- To search for potential breach based from various log sources (i.e. Firewall, EDR, log storage) on the IOC provided by the TI
- To be able to allow the incident response team be able to identify what are the affected application attempting to make the connection
- To create a case for incident response team to close
- To inform incident response team of any potential breach

5. To create a blocking rule in firewall based on the IP address
- To detect or correlate alerts from EDR and Firewall logs to detect anomaly behaviour on the followings
  - Execution of unusual process on the server;
  - Unauthorised changes of a registry key of the server; 
  - Connection of Network Abnormality Connection (e.g. potential C2 connectivity); 
  - Detection of suspicious Activities based on behavioural/heuristic based;
  - Detect other types of unusual activities;

6. To inform the incident response team of an incident via email alerts
- Case management in managing the incident with multiple stakeholders (e.g. incident response team, business users and management).

7. To show demonstrate
- How the different teams can use the playbook to perform incident management and reporting where possible.

8. To be able to perform these containment actions:
- To automatically trigger the EDR to contain and isolate vulnerable endpoints from the network
- To execute two types of AV scan on affected endpoints Investigate
- To disable/delete the affected accounts

9. To allow user to perform investigation:
- To investigate the extend of the malware spread (could be show case affected to another windows/linux server) and able to isolate quickly
- To be able to collect this information on the affected server:
  - Account (local or domain)
  - Memory dumps
  - Suspicious files (zipped and password protected)
  - Hashes
  - Registry hives
  - Logs pertaining to the incident

10. To allow user to perform recovery action:
- Enable back the impacted user accounts
- Recover the vulnerable machine based on the good working copy for virtual server, If necessary, to rebuild or re-provision the impacted system
- Reconnect back the affected the machine to the network after the system is cleared for connection

the points are quite scattered and have overlaps, can you organize the information such that the flow and demonstration is smooth?
</details>

Certainly! To make the demonstration of EDR (Endpoint Detection and Response) and SOAR (Security Orchestration, Automation, and Response) solutions smooth and cohesive, we can organize the use cases into a logical flow that aligns with incident detection, response, containment, investigation, and recovery. Here’s a structured approach:

---

### **1. Incident Detection and Response**

**1.1 Automated Response to Zero-Day Vulnerabilities**

- **Use Case:** Implement an automated response plan for zero-day vulnerabilities like Log4J or Polyfill.
  - **Actions:**
    - Collect indicators suspected of exploiting relevant CVEs or through email.
    - Perform active search detection based on reported signatures.
    - Execute virtual patching to reduce the attack surface.

**1.2 Anomaly Detection and Threat Hunting**

- **Use Case:** Automatically perform threat hunting to detect anomalies, such as an application connecting to a malicious IP.
  - **Actions:**
    - Receive Threat Intelligence (TI) from sources like VirusTotal, AlienVault, or OTX.
    - Search for potential breaches based on IOC from TI.
    - Identify affected applications making the connection.
    - Create a case for incident response and inform the team of potential breaches.

**1.3 Suspicious Activities Investigation**

- **Use Case:** Investigate suspicious activities such as misused accounts or high login failures.
  - **Actions:**
    - Detect or correlate alerts from logs (Azure Log Analytics, AWS CloudTrail) to identify login failures or misuse.
    - Determine which processes/applications are using the accounts and how activities are triggered.
    - Inform the incident response team via email.
    - Allow disabling of the account if needed.

---

### **2. Containment Actions**

**2.1 Blocking and Isolation**

- **Use Case:** Create a blocking rule in the firewall based on IP addresses.
  - **Actions:**
    - Ingest CSV files from email servers using a specific template.
    - Make changes in the firewall to block outbound connections, requiring an approval workflow.

**2.2 Endpoint Containment**

- **Use Case:** Automatically contain and isolate vulnerable endpoints from the network.
  - **Actions:**
    - Trigger EDR to isolate endpoints.
    - Execute two types of AV scans on affected endpoints.
    - Disable or delete affected accounts.

---

### **3. Investigation**

**3.1 Extent of Malware Spread**

- **Use Case:** Investigate the extent of malware spread and isolate affected systems.
  - **Actions:**
    - Collect information from affected servers, including:
      - Account details (local/domain)
      - Memory dumps
      - Suspicious files (zipped/password-protected)
      - Hashes
      - Registry hives
      - Logs related to the incident

**3.2 Alert Correlation**

- **Use Case:** Detect and correlate alerts from EDR and firewall logs for unusual behavior.
  - **Actions:**
    - Monitor execution of unusual processes.
    - Detect unauthorized changes to registry keys.
    - Identify network abnormalities and potential C2 connectivity.
    - Recognize other types of suspicious activities based on behavioral or heuristic analysis.

---

### **4. Recovery**

**4.1 System Recovery and Restoration**

- **Use Case:** Recover and restore affected systems and accounts.
  - **Actions:**
    - Enable impacted user accounts.
    - Recover or rebuild vulnerable machines based on good working copies.
    - Reconnect machines to the network once cleared.

**4.2 Incident Management and Reporting**

- **Use Case:** Manage incidents and report to stakeholders.
  - **Actions:**
    - Case management with multiple stakeholders (incident response team, business users, management).
    - Demonstrate how different teams use playbooks for incident management and reporting.

---

By organizing the use cases in this manner, you ensure a logical progression from detection to response, containment, investigation, and recovery. This flow allows for a comprehensive demonstration of EDR and SOAR solutions, showcasing their capabilities in a structured and efficient manner.
