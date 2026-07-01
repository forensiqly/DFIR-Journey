## Day 7: Windows Persistence Investigation, Run Keys

#### Overview

Today focused on understanding Windows persistence mechanisms and how forensic investigators identify how programs are configured to run automatically after login.

The main focus was Registry Run Keys and understanding the difference between legitimate persistence and suspicious persistence.


#### Topics Covered

##### 1. Windows Persistence

Persistence is a technique used to maintain access or ensure a program continues running after a restart or user login.

Common Windows persistence locations include:

* Registry Run Keys
* Startup Folder
* Scheduled Tasks
* Services


#### Registry Run Keys

##### HKCU Run Key

Location:

HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run

Purpose:

1. Executes programs when the current user logs in.
2. Only affects the current user account.

##### HKLM Run Key

Location:

HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run

Purpose:

1. Executes programs for all users on the machine.
2. Usually requires higher privileges to modify.


#### Practical Investigation

Reviewed:

##### HKCU Run Key

Observed 5 entries.

Recognized applications included:

1. Canva
2. Microsoft Edge
3. Adobe
4. OneDrive

##### HKLM Run Key

Observed 4 entries.

Recognized system/software components included:

1. RtkAudUService
2. SecurityHealth
3. WavesSvc

The entries appeared consistent with legitimate installed software.


#### Artifact Validation

Investigated:

RtkAudUService

Value Data:

C:\WINDOWS\System32\DriverStore\FileRepository\realtekservice.inf_amd64_c607c18cb15933d8\RtkAudUService64.exe -background

Analysis:

The executable location matched a Realtek driver-related directory, which was consistent with the Realtek audio component found in Device Manager.

This reinforced the importance of validating:

1. File name
2. File location
3. Software context
4. System behavior


#### Key DFIR Lessons

1. A persistence mechanism does not automatically mean malicious activity.
2. An artifact becomes suspicious when it is inconsistent with expected system behavior.
3. File paths provide important context.
4. Attackers can use legitimate-looking names to disguise malicious files.
5. Investigators should avoid making conclusions without sufficient evidence.


#### Next Steps

Continue investigating other Windows persistence mechanisms, including:

1. Scheduled Tasks
2. Services
3. Startup Folder

Goal: Understand how attackers maintain access and how investigators identify abnormal behavior.
