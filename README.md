# microsoft-defender-security-intelligence-update-investigation

A hands-on Microsoft Defender SOC lab focused on verifying Security Intelligence (signature) updates using Windows Security, PowerShell, and Windows Defender Operational logs.

---

## 🎯 Objectives

This lab demonstrates how a Security Operations Center (SOC) analyst verifies that Microsoft Defender Antivirus is running the latest security intelligence updates.

During this lab, you will:

- Review Microsoft Defender Security Intelligence versions
- Perform a manual signature update
- Verify Defender health using PowerShell
- Investigate Windows Defender Operational logs
- Document update-related events
- Practice endpoint health validation

---

## 🛠️ Lab Environment

| Component | Details |
|----------|---------|
| Operating System | Windows 10 x64 |
| Endpoint Protection | Microsoft Defender Antivirus |
| Tools | Windows Security, PowerShell, Event Viewer |
| Platform | VMware Workstation |

---

# Lab Architecture

```
Windows 10 VM
        │
        ▼
Microsoft Defender Antivirus
        │
        ▼
Security Intelligence Update
        │
        ├────────► Windows Security
        │
        ├────────► PowerShell
        │
        └────────► Event Viewer
                      │
                      ▼
        Windows Defender Operational Logs
```

---

# Skills Practiced

- Microsoft Defender Administration
- Endpoint Security
- Windows Event Log Analysis
- PowerShell
- Security Intelligence Verification
- SOC Documentation
- Endpoint Health Monitoring

---

# Tools Used

- Microsoft Defender Antivirus
- Windows Security
- PowerShell
- Event Viewer

---

# Lab Workflow

```
Open Windows Security
        │
        ▼
Review Protection Updates
        │
        ▼
Check for Updates
        │
        ▼
Update-MpSignature
        │
        ▼
Verify Update
(Get-MpComputerStatus)
        │
        ▼
Investigate Operational Logs
        │
        ▼
Document Findings
```

---

# PowerShell Commands Used

## Update Microsoft Defender Signatures

```powershell
Update-MpSignature
```

---

## Verify Defender Status

```powershell
Get-MpComputerStatus
```

---

## Display Signature Version

```powershell
Get-MpComputerStatus | Select AntivirusSignatureVersion, AntivirusSignatureLastUpdated
```

---

## Check Defender Service

```powershell
Get-Service WinDefend
```

---

## Check Windows Update Service

```powershell
Get-Service wuauserv
```

---

# Event Viewer Location

```
Applications and Services Logs
└── Microsoft
    └── Windows
        └── Windows Defender
            └── Operational
```

---

# Investigation Summary

The endpoint's Microsoft Defender Security Intelligence version was reviewed and updated using both the Windows Security interface and PowerShell.

Defender health was verified using `Get-MpComputerStatus`, confirming that:

- Antivirus was enabled
- Real-time protection was active
- Security Intelligence signatures were current

Windows Defender Operational logs were then reviewed to validate update activity and verify endpoint protection readiness.

---

# SOC Analyst Observations

- Microsoft Defender successfully validated Security Intelligence.
- Endpoint protection remained operational throughout the investigation.
- No malware detections occurred during this activity.
- Update-related events were successfully generated within Defender Operational logs.

---

# MITRE ATT&CK Relevance

Although this lab is administrative, keeping Defender signatures current strengthens detection capabilities against techniques spanning multiple ATT&CK tactics:

- Initial Access
- Execution
- Persistence
- Defense Evasion
- Credential Access
- Discovery
- Collection

---

# Learning Outcome

This lab demonstrates how SOC analysts validate endpoint readiness by confirming Microsoft Defender Security Intelligence updates, verifying Defender health using PowerShell, and investigating Defender Operational logs.
