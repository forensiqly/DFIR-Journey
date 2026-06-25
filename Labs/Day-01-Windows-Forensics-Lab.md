## Day 01: Windows Forensics Lab Report

### Case Information

Case ID:
DFIR-001

Analyst:
FORENSIQly

Date:
24 June 2026

Objective:
Perform basic Windows forensic analysis using built-in Windows artifacts.


### Scope

Artifacts analyzed:

1. Windows Event Logs
2. Windows Registry


### Tools Used

1. Windows Event Viewer
2. Windows Registry Editor


### Evidence Reviewed

#### Authentication Logs

Event IDs analyzed:

1. 4624 Successful Logon
2. 4625 Failed Logon

Findings:

Successful logon activity was observed from the SYSTEM account through services.exe.

The activity was consistent with normal Windows service behavior.

A failed logon attempt was identified and originated from localhost (127.0.0.1).

No evidence of remote authentication attempts was identified.


### Registry Analysis

Artifacts reviewed:

1. Run Keys
2. Uninstall Key

Findings:

Startup applications were reviewed through:

HKCU\Software\Microsoft\Windows\CurrentVersion\Run

and

HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run

Observed entries appeared consistent with legitimate software.

Installed software information was reviewed through the Uninstall Registry key.


### Investigation Timeline

24 June 2026

1. Reviewed Windows authentication events
2. Investigated Event ID 4624
3. Investigated Event ID 4625
4. Reviewed Registry Run Keys
5. Reviewed installed software artifacts


### Conclusion

The analyzed artifacts showed normal Windows activity.

No suspicious persistence mechanisms or unauthorized software installations were identified during this investigation.


### Lessons Learned

This investigation improved understanding of:

1. Windows authentication events
2. Registry artifacts
3. Persistence mechanisms
4. Evidence-based analysis
