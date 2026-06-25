## Windows Registry Uninstall Key Investigation

### Objective

Analyze the Windows Registry Uninstall key to understand how installed software information can be used as forensic evidence.

### Artifact

Windows Registry Uninstall Key


### Location

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall


### Purpose

The Uninstall key stores information about software installed on a Windows system.

Common values include:

1. Display Name
2. Display Version
3. Publisher
4. Install Date
5. Install Location
6. Estimated Size


### Findings

Approximately 30 software-related entries were observed.

Recognized software included:

1. Cisco Packet Tracer
2. Python-related components


No unexpected or suspicious software entries were identified during this review.


### Forensic Value

The Uninstall key can help investigators answer questions such as:

1. What software exists on the machine?
2. When was software installed?
3. Who published the software?
4. Where is the software installed?
5. Could recently installed software be related to an incident?


### Analysis

Installed software information can provide timeline clues during investigations.

For example, if suspicious software was installed shortly before a security incident, the installation date and publisher information may become important evidence.

However, absence from the Uninstall key does not prove that software was never executed because some malware may not register itself as installed software.


### Conclusion

The reviewed Uninstall Registry artifact contained expected software entries.

No suspicious installations were identified during this investigation.
