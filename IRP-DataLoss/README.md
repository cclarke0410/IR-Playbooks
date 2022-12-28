# Data Loss Playbook

[[_TOC_]]

## Scope
This Playbook covers the steps to take in case of Data Loss / Data Breach.

## 1. Preparation

<details>
<summary>Expand/Colapse</summary>

- Create and maintain a list of 
    - all domains owned by Company.
        - This can prevent you from taking actions against our own domains
    - all people of can register domains
- Create email template 
    - to notify all employees of ongoing phishing campaing against the organization 
    - to contact hosting companies for domain take down
    - to inform 3rd party to take actions against phishing on there infra (Microsoft, Fedex, Apple, etc.)
- Ensure that:
    - Mail anti-malware/anti-spam/anti-phish solutions are in place.
    - Users know how to report phish
    - Detection exists for office documents spawning processes
        - PowerShell
        - CMD
        - WMI
        - MSHTA
        - Etc.
- Perform Firedrill to ensure all aspects of the Playbook are working
    - After publication
    - At least once a year
    - Test/Validate: 
        - [Customer's Cards](Customers)
        - Internal Contact and Escalation Paths
- Review threat intelligence for 
    - threats to the organisation, 
    - brands and the sector, 
    - common patterns 
    - newly developing risks and vulnerabilities
- Ensure  appropriate  access  to  any  necessary  documentation  and  information, including out-of-hours access, for the following
    - IR Playbgns to highlight information security risks faced by employees, including: 
    - Phishing attacks and malicious emails;
    - Ransomware;
    - Reporting a suspected cyber incident.

### Tool Access and Provisioning

#### Tool1
Please referer to [Tool1 Documentation](../Products/TOOL.md)

#### Tool2
Please referer to [Tool2 Documentation](../Products/TOOL.md)

### Assets List
- A list of assets and owner should exists and be available for the following
    - Customers Assets
        - Owners
        - Contacts
        - Pre authorized actions
    - Company Assets (Including all filiale and business units)
        - Owners
        - Contacts
        - Administrators
        - Pre autorized actions
- Type of assets inventory needed
    - Endpoints
    - Servers
    - Network Equipements
    - Security Appliances
    - Network Ranges
        - Public
        - Private
        - VPN / Out of Band
            - Employees
            - Partners
            - Clients

</details>

## 2. Detect
<details>
<summary>Expand/Colapse</summary>

### Workflow
<details open>
<summary>Expand/Colapse</summary>

![Data Loss Workflow](Workflows/DataLoss-Workflow-Detect.png)

</details>

### DD1. Identify Threat Indicators
<details open>
<summary>Expand/Colapse</summary>

#### Alerts
Alerts are be generated by differents systems owned by the Security/SOC team. The main sources for alerts are  
- Tickets
- SIEM
- Anti-Virus / EDR
- Reports
    - DNS
    - Web Proxy

#### Notifications
Notifications are comming from external sources usually via email, Teams or phone. The main sources for notifications are  
- System Administrators
- Clients
- Third Parties
- ISP

</details>

### DD2. Indentify Risks Factors
<details open>
<summary>Expand/Colapse</summary>

#### Common
- Credential Theft
- Device Loss
    - Laptop
    - Phone
- Criminal Activites
    - Blackmail / Ransom

#### Company Specific
- Reputation Damage
- Financial Losses
    - Lost of conctrat
    - Contract not renewed
    - Lower bid to our clients
    - Fines
        - Regulation

</details>

### DD3. Data Colletion
This section describe the information that should be collected and documented about the incident  
There is a lot of ressources to help you with that phase [here](../Tools/README.md)
<details open>
<summary>Expand/Colapse</summary>

Type Data
- Personally identifiable information (PII) 
- Intellectual Property
- Age of the Data 
    - Current
    - Old
- Owner of the Data
    - Company
    - Clients

</details>

### DD4. Categorize
<details open>
<summary>Expand/Colapse</summary>

Determine type of Data Loss we are dealing with.
- Cyber Threat
- Insider Threat
- Mail Sent to Wrong Destination
- Device Lost
    - Laptop
    - Phone
- Printed Documents

</details>

### DD5. Is it Ransomware ?

If the Data Loss is caused by a Ransomware please refere to the ![Ransomware Playbook](../IRP-Ransomware/)  

### DD6. Triage 
<details open>
<summary>Expand/Colapse</summary>

- Determine Impact
- Determine Scope 
    - Number of Documents / Records
    - Number of Clients
    - Number of Company Entities
    - Number of Individuals
- Send Communincation
- Determine if False Positive

</details>
</details>
</details>

## 3. Analyze
<details open>
<summary>Expand/Colapse</summary>

### Workflow
<details open>
<summary>Expand/Colapse</summary>

![Data Loss Workflow](Workflows/DataLoss-Workflow-Analyze.png)

</details>

### DA1. Verify
<details open>
<summary>Expand/Colapse</summary>

In conjonction with a senior member of the SOC  
- Double check previous data
- Rule Out False Positive

</details>

### DA2. Critical Incident
If this incident is deemed **Major or Critical** by the senior analyst go to the [Critical Incident Playbook](../IRP-Critical/)

### DA3. Identify IOCs
<details open>
<summary>Expand/Colapse</summary>

- Data
    - All Files Lost
    - Records Stolen
    - MFA Token
    - Credentials
    - PII
- Validate hashes
    - [VirusTotal](../Tools/README.md#virus-total)
    - [Hybrid Analysis](Tools/README.md#hybrid-analysis)
- Validate links
    - [VirusTotal](../Tools/README.md#virus-total)
    - [Hybrid Analysis](../Tools/README.md#hybrid-analysis)
    - [URLScan](../Tools/README.md#urlscan)
- ID other addresses, domains, IPs
    - [VirusTotal](../Tools/README.md#virus-total)
    - [Hybrid Analysis](../Tools/README.md#hybrid-analysis)
    - [Talos Intelligence](../Tools/README.md#hybrid-analysis)
- Search Threat Intel sources
    - [VirusTotal](../Tools/README.md#virus-total)
    - [Hybrid Analysis](../Tools/README.md#hybrid-analysis)
    - [Talos Intelligence](../Tools/README.md#hybrid-analysis)
- Disk forensics on recipient's endpoint

</details>

### DA4. Malware
If **Malware** was involve in the incident refer to the [Malware Playbook](../IRP-Malware/)  

### DA5. What Was Accessed
<details open>
<summary>Expand/Colapse</summary>

Did the attack touched other systems?  
Look for:  
- Signs of Lateral Movement
- Review Firewall Logs
- Review Netflows
- Assess the Number of Hosts Involved
- Number of Clients Affected
    - Perform the same research for all affected clients

</details>

### DA6. Update Scope
<details open>
<summary>Expand/Colapse</summary>

- Update lists of affeected
    - Data
    - Endpoints
    - Company Entities
    - Clients

</details>

### DA8. Scope Validation
<details open>
<summary>Expand/Colapse</summary>

Have all the machines and data been identified? 
If you find futher traces of phishing or new IOCs go back to [Verify Step](README.md#verify).  

When you are done identifying all :  
- Data that was Lost
- Affected Endpoints
- Affected Company Entities
- Affected Customers

And if applicable investigated all:  
- URLs
- Domains
- IP
- Ports
- Files
- Hash

You can proceed with the next steps.  

</details>

### DA9. External Help
Does Company have all the knowledge and ressources to handle the crisis alone?

#### DA11. Technical Help
If the Incident Commander feels we need Technical help or ressources to handle the incident he can reach out to our Incident Response Partner.  
We have a retainer with the following company and we can reach them at : xxxx@yyy.com or 555-555-5555

#### DA12. Legal Help
If there are Legal implication such as
- GDPR
- Criminal Charges
- Regulation
- Laws


### DA14. Root Cause Analysis
<details open>
<summary>Expand/Colapse</summary>

Identify how this incident happened. 
- Phishing Emails
- Voice Phishing
- Drive-by Download
- Vulnerability
    - Remote Code Execution
    - Cross-Site Scripting
- Remote Services
    - Default / Weak Password
    - Brute Force
    - Vulnerability
- Lost Device
- Human Error

</details>

### DA15. Send Communincation
<details open>
<summary>Expand/Colapse</summary>

Contact any relevant of the following party
- Internal Security Team
- Affected Clients
- Any internal teams needed for remediation or counselling 

</details>

</details>


## 4. Contain / Eradicate
<details open>
<summary>Expand/Colapse</summary>

### Workflow
<details open>
<summary>Expand/Colapse</summary>

![Data Loss Workflow](Workflows/DataLoss-Workflow-Contain_Eradicate.png)

</details>

### DC1. Compromised Credentials
<details open>
<summary>Expand/Colapse</summary>

If any credentials are suspected to have been accessed, stolen or used they will all need to be changed.  
This applies to:  
- Local Passwords
- Network Passwords
- Remote Passwords
- Etc.

</details>

### DC3. Compromised or Lost MFA
<details open>
<summary>Expand/Colapse</summary>

If any Multi Factor Authentication token/code were accessed, stolen or used they will all need to be 
- Revoke
- Replace.  

</details>

### DC5. Customer Data
<details open>
<summary>Expand/Colapse</summary>

If any if customer data was accessed or leaked we will need to send communication to all affected clients using the approved [Customer Communication Template]().  

</details>

### DC7. Data Posted to the Internet
<details open>
<summary>Expand/Colapse</summary>

If the site is controlled by an public company, we can ask them to remove the information. Usually writing at <abuse@company.com> is a good place to start.

</details>

### DC9. Insider Threat
<details open>
<summary>Expand/Colapse</summary>

If the information was intentionally leaked/sold by an employee, we need to:  
- Contact HR
- Disable User Account
- Disable any MFA token

We will potentially need to send physical security to the employee's desk to seize his/her laptop and other devices. 

</details>

### DC11. Attacker Still Have Access?

If there is any sign of the attacker still being in the network, go to the [Malware Playbook](../IRP-Malware/README.md)  


### DC12. Close Monitoring
<details open>
<summary>Expand/Colapse</summary>

- Monitor for 
    - New information leaked
    - New communication from Attackers
    - People trying to give back device(s)/document(s)

</details>


### DC13. All Affected Data Lost Addressed?
<details open>
<summary>Expand/Colapse</summary>

If all affected data have been addressed, you can go to the [Recover phase](README.md#5-recover), otherwise continue bellow.  

</details>

### DC14. New Data Lost Discovered?
<details open>
<summary>Expand/Colapse</summary>

If there was new leaked data/devices discovered, go back to the [Analyze Phase](README.md#3-analyze)

</details>
</details>


## 5. Recover
<details open>
<summary>Expand/Colapse</summary>

### Workflow
<details open>
<summary>Expand/Colapse</summary>

![Data Loss Workflow](Workflows/DataLoss-Workflow-Recover.png)

</details>

### DR1. Rebuilt Systems
<details open>
<summary>Expand/Colapse</summary>

In an isolated environment:  
    - Install 
        - Supported OS
        - Security solutions
        - Up to date applications
    - Restore data (from a clean backup)

</details>

### DR2. Vulnerability Scan
<details open>
<summary>Expand/Colapse</summary>

Perform:  
- External VA
- If possible
    - Authenticated scan
    - Agent base scan

</details>

### DR3. Update Defenses
<details open>
<summary>Expand/Colapse</summary>

Determine which of the following rules needs to be removed and which needs to stay in the following list:  
- Firewall Rules
- EDR 
    - Ban hashes
    - Ban domains
    - Containment
- Proxy Block
- DNS Sinkhole
- Etc. 

</details>

### DR4. Restore Service
<details open>
<summary>Expand/Colapse</summary>

Depending on the containment applied to the host, perform all the following that applies:  
- Lift containment in EDR console
- Move host to production VLAN
- Enable switch port
- Enable/Create virtual network interface
- etc. 

</details>

### DR5. All Affected Endpoints Restored?
<details open>
<summary>Expand/Colapse</summary>

If all affected endpoints have been restored, you can go to the [Post Incident](README.md#6.-post-incident) phase, otherwise continue bellow.  
- List systems that haven't been restored
- Go to [README.md#rebuild-systems]

</details>

</details>


## 6. Post Incident
<details>
<summary>Expand/Colapse</summary>

### Workflow
<details open>
<summary>Expand/Colapse</summary>

![Data Loss Workflow](Workflows/DataLoss-Workflow-Post_Incident.png)

</details>

### DP1. Incident Review
<details open>
<summary>Expand/Colapse</summary>

- What worked
- What didn't work

</details>

### DP2. Update Mode of Operations
<details open>
<summary>Expand/Colapse</summary>

Update the following documents as requiered:  
- Policies
- Processes
- Procedures
- Playbooks
- Runbooks

Update Detetion Rules in:  
- SIEM
- Anti-Spam
- Malware Gataway
- EDR
- Other security solution

</details>

### DP3. Review Defensive Posture
<details open>
<summary>Expand/Colapse</summary>

- Schedule review of newly introduced rules in6 months
- Are the following still applicatble
    - Firewall Rules
    - Proxy Rules for C2
    - AV / EDR custom Signatures
    - IPS Signatures

</details>

### DP4. Build New Detection
<details open>
<summary>Expand/Colapse</summary>

If the Data Loss was not caused by a lost device, we need to build new detections
- Mail Service
- Anti-Spam / Anti-Phish
- ATT&CK Techniques
- etc. 

</details>

### DP5. Modifify Base Images
<details open>
<summary>Expand/Colapse</summary>

If the Data Loss was caused by a lack of hardening or sufficient patch level: 
- Review hardening processes
- Include critical patches in base Images
- etc. 

</details>

### DP7. User Awareness Training
<details open>
<summary>Expand/Colapse</summary>

If the incident was caused by a human error
- Create / Select new mandatory training
    - Cyber Education Vendor
    - From Youtube videos
    - Built by internal teams

</details>

### DP8. Calculate Incident's Cost
<details open>
<summary>Expand/Colapse</summary>

Calculate the incident's Cost
- Time Spent
- Ransom paid
- Downtime
- Fines / Penalities
- etc. 

</details>

</details>

# References

This Playbook was built using the following references:  
https://www.dfir.training/index.php?option=com_jreviews&format=ajax&url=media/download&m=14tt1&1600804844570  
https://www.gov.scot/publications/cyber-resilience-incident-management/  
https://github.com/certsocietegenerale/IRM/tree/master/EN  
https://www.incidentresponse.com/playbooks/  
https://ayehu.com/cyber-security-incident-response-automation/top-5-cyber-security-incident-response-playbooks/  
https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf  