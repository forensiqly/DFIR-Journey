## Day 01: Windows Authentication Investigation

#### **Objective**

Analyze Windows authentication events using Event Viewer to understand normal login activity and identify important forensic artifacts.

#### Tool Used

Windows Event Viewer


### Investigation 1: Successful Logon

#### Event Details

Event ID:
4624

Description:
Successful account logon

Logon Type:
5 (Service Logon)

Account:
SYSTEM

Process:
C:\Windows\System32\services.exe

Logon Process:
Advapi

Authentication Package:
Negotiate

Elevated Token:
Yes


#### Analysis

The event represents a service authentication performed by the SYSTEM account.

The process responsible was services.exe, which is the Windows Service Control Manager responsible for managing system services.

The authentication was handled through Advapi using the Negotiate authentication package.

No source network address was observed, suggesting the authentication occurred locally rather than from a remote system.

The activity appears consistent with normal Windows service behavior.


### Investigation 2: Failed Logon

#### Event Details

Event ID:
4625

Date/Time:
22/06/2026 01:55:52

Logon Type:
2 (Interactive Logon)

Failure Reason:
An error occurred during logon

Source Network Address:
127.0.0.1


#### Analysis

The failed authentication attempt originated from localhost (127.0.0.1), indicating that the activity came from the local machine.

No target account name was recorded.

The available evidence does not indicate a remote login attempt.


### Key Lessons

- Event IDs identify specific Windows events.
- Logon Type explains how authentication occurred.
- SYSTEM account activity is common for Windows services.
- Context is required when analyzing security events.


### Conclusion

The investigated authentication events appear consistent with normal Windows activity.

No suspicious authentication behavior was identified during this investigation.
