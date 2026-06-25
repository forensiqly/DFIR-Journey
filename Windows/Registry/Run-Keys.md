## Windows Registry Run Keys Investigation

### Objective

Analyze Windows Registry Run Keys to understand startup persistence mechanisms and their forensic value.

### Artifact

Registry Run Keys

### Locations Investigated

#### User-Level Persistence

HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run


#### Machine-Level Persistence

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run


### Findings

#### HKCU Run Key

Observed entries:

1. Adobe Acrobat Synchronizer
2. Microsoft Edge
3. OneDrive

These entries are configured to start automatically when the user logs in.


#### HKLM Run Key

Observed entries:

1. RtkAudService
2. SecurityHealth
3. WavesSvc

These entries are configured at the system level and affect users across the machine.


### Analysis

Run Keys are valuable forensic artifacts because attackers can use them to establish persistence.

An investigator can use Run Keys to determine:

1. What programs start automatically
2. Whether suspicious software persists after reboot
3. Whether startup behavior is expected or abnormal

The observed entries appeared consistent with legitimate installed software.


### Key Lesson

Registry artifacts should not be analyzed in isolation.

A suspicious entry requires additional context such as:

1. File location
2. Publisher
3. Execution history
4. Timeline information


### Conclusion

No suspicious persistence mechanisms were identified during this investigation.
