# Project: Digital Forensics & Data Theft Investigation

**Objective:** To conduct a digital forensic investigation into a suspected data breach incident by analyzing filesystem artifacts, reconstructing user activity timelines, and mapping findings to the MITRE ATT&CK® framework to determine the scope of compromise and provide evidence-based defensive recommendations.

## 📋 Scenario Overview

**Alert:** Suspected unauthorized data access and exfiltration by a user.

**Goal:** Identify what data was accessed, how it was collected, and provide actionable intelligence to prevent future incidents.

## 🔍 Investigation Process

### 1. Forensic Evidence Acquisition
- Acquired and analyzed key forensic artifacts including:
  - System command history
  - File metadata and directory listings
  - File transfer and archive creation logs
  - User activity timelines

### 2. Timeline Reconstruction & Analysis
- Correlated timestamps across multiple data sources to establish a precise sequence of events
- Identified unauthorized access to sensitive directories and files
- Tracked file creation, modification, and access patterns

### 3. IOC Extraction & TTP Mapping

**Key Findings:**
- Creation of unauthorized compressed archives containing sensitive data
- Use of staging directories to consolidate files before exfiltration
- Attempts to clear or obfuscate activity in system history

**MITRE ATT&CK Mapping:**

| Tactic | Technique | Description |
|--------|-----------|-------------|
| **Collection** | T1005: Data from Local System | Sensitive files were gathered from the local system |
| **Collection** | T1560.001: Archive via Utility | Data was compressed into archives using system utilities |
| **Collection** | T1074.001: Local Data Staging | Files were collected in a staging directory before exfiltration |
| **Defense Evasion** | T1070: Indicator Removal | Attempts to erase evidence of activity from system history |

### 4. Scope & Impact Assessment
- Determined the specific set of files and databases that were accessed and archived
- Assessed the potential impact of the data breach based on the sensitivity of the exfiltrated information
- Identified data classification levels of compromised information

## 🛠️ Tools & Techniques Used
- **Forensic Analysis:** Timeline reconstruction, file metadata examination
- **Incident Response:** Evidence collection, chain of custody documentation
- **Framework:** MITRE ATT&CK®
- **Platform:** KC7 Cyber Range
- **Analysis Methods:** File system analysis, timestamp correlation, pattern recognition

## ✅ Conclusion & Recommendations

**Assessment:** Confirmed data theft incident involving unauthorized collection and archiving of sensitive information.

**Immediate Actions:**
1. **Contain:** Immediately revoke the user's access privileges
2. **Investigate:** Expand investigation to determine if exfiltration was completed
3. **Block:** Implement monitoring for archive utility execution on sensitive servers

**Long-Term Recommendations:**
- Implement strict access controls and auditing for sensitive directories
- Establish user behavior analytics to detect unusual data access patterns
- Conduct regular audits of user activity on critical systems
- Enhance employee training on data handling policies
- Implement data loss prevention (DLP) solutions

## 🎯 Lessons Learned

> "This investigation highlighted the importance of monitoring not just external threats but also internal risks. The attacker used simple, legitimate tools to perform data collection, making detection without proper auditing difficult."

> "I learned to look for patterns across multiple data sources - the full story emerged only when correlating system history with file metadata and directory listings."

> "The case demonstrated how critical proper logging and monitoring are for detecting insider threats and unauthorized data access."

---

**Note:** This investigation was conducted through the KC7 "A Scandal in Victoria" module, a simulated forensic investigation designed to replicate real-world data breach scenarios. All indicators have been redacted for security purposes.

*📫 Connect with me to discuss digital forensics or incident response techniques!*
