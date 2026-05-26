Overview
This project demonstrates a hands-on SOC (Security Operations Center) lab environment built using Splunk Enterprise, Splunk Universal Forwarder, Kali Linux, and a Windows virtual machine.

The objective of this lab was to simulate brute-force authentication activity, collect Windows Event Logs, forward them into Splunk, analyze security events using SPL queries, and visualize the data through dashboards.



Lab Architecture

Kali Linux → Windows VM → Splunk Universal Forwarder → Splunk Enterprise



Technologies Used

- Splunk Enterprise
- Splunk Universal Forwarder
- Kali Linux
- Windows 10 VM
- VMware
- SPL (Search Processing Language)


Project Workflow

1. Simulated RDP Brute-Force Attack
- Generated authentication attempts from Kali Linux to the Windows VM.
- Observed failed and successful login behavior.

<img width="1919" height="1021" alt="Screenshot 2026-05-26 101950" src="https://github.com/user-attachments/assets/c332b2ca-d66f-49b6-8e5b-9cf9b2bb67cf" />




2. Windows Event Log Collection
Collected important Windows Security Logs including:
- Failed Logons
- Successful Logons
- Privileged Logons
- Process Creation Events


<img width="1919" height="1025" alt="Screenshot 2026-05-26 103506" src="https://github.com/user-attachments/assets/e50589c6-8091-482c-9151-774e3246bc74" />



3. Splunk Setup
- Installed Splunk Enterprise
- Configured Splunk Universal Forwarder
- Enabled receiving on port 9997
- Forwarded Windows Event Logs into Splunk





4. Log Analysis using SPL Queries
Analyzed and filtered logs using SPL queries to identify:
- Failed login attempts
- Authentication trends
- User activity
- Workstation activity
- Security event statistics



<img width="1919" height="969" alt="Screenshot 2026-05-26 185033" src="https://github.com/user-attachments/assets/89a50f4d-3b32-4bb5-be90-0ec7b7b343cb" />







<img width="1919" height="971" alt="Screenshot 2026-05-26 194413" src="https://github.com/user-attachments/assets/c94d6ab8-8b87-4632-bb4e-7234de04377f" />






<img width="1915" height="976" alt="Screenshot 2026-05-26 195932" src="https://github.com/user-attachments/assets/e8ceae92-3946-47b6-9ff1-36402fe10105" />






5. Dashboard Creation
Created dashboards for:
- Failed Logon Monitoring
- Authentication Analysis
- Security Event Visualization
- Event Statistics





<img width="1919" height="976" alt="Screenshot 2026-05-26 210651" src="https://github.com/user-attachments/assets/f4fb4048-dbb8-411d-be83-55fc05b71c98" />






Important Windows Event IDs

| Event ID | Description |
|----------|-------------|
| 4625 | Failed Logon |
| 4624 | Successful Logon |
| 4672 | Special Privilege Logon |
| 4688 | Process Creation |






Example SPL Queries:<br> 
<br>
</>SPL <br> 
Failed Login Attempts<br>
index=* EventCode=4625

</>SPL<br>
Successful Logons<br>
index=* EventCode=4624

</>SPL<br>
Failed Login Count by User<br>
index=* EventCode=4625
| stats count by Account_Name

</>SPL<br>
Process Creation Events<br>
index=* EventCode=4688

Skills Gained:
*SIEM Configuration
*Log Forwarding
*Windows Event Analysis
*SPL Query Writing
*Threat Detection
*Authentication Monitoring
*Dashboard Visualization
*Basic SOC Investigation Workflow


Learning Outcome

This project helped in understanding how security events generated during attacks can be collected, monitored, filtered, and investigated within a SIEM environment.

Disclaimer

This project was performed in a controlled virtual lab environment for educational and defensive cybersecurity learning purposes only.
