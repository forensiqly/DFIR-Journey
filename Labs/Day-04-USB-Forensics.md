## Day 4: USB Device Forensics

#### Topic
USB artifacts and Windows device enumeration

#### Objective
Understand how Windows records USB devices and what evidence USB artifacts can provide during a forensic investigation.


### Key Concepts Learned

#### USB vs USBSTOR

USB:

Contains information about general USB devices detected by Windows.

Examples:
1. Keyboard
2. Mouse
3. Webcam
4. Audio devices
5. USB adapters


USBSTOR:

Contains information specifically about USB storage devices.

Examples:
1. Flash drives
2. External hard drives

Important:
The absence of USBSTOR does not prove that no USB device was connected.


### Registry Locations

#### USB Devices

Path:
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USB

Purpose:
Shows USB devices recognized by Windows.

Can reveal:
1. Vendor ID
2. Product ID
3. Device identifiers


#### USB Storage Devices

Path:
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR


Purpose:
Shows USB mass storage devices connected to the system.


### VID and PID

Example:
VID_0BDA&PID_5538


VID:
Vendor ID
identifies the manufacturer.


PID:
Product ID
identifies the specific device.


### Investigation Exercise

Scenario:

A company suspects an employee copied confidential.docx to a USB device.


Evidence:

1. Recent Items shows confidential.docx was accessed.
2. Prefetch shows WINWORD.EXE was executed.
3. USB Registry shows a Realtek USB device.
4. USBSTOR shows no storage devices.


#### Evidence Observed

The system shows evidence of:
1. Microsoft Word execution.
2. confidential.docx access.
3. A detected USB device.

No evidence of a USB storage device was identified.


### Analysis

The evidence supports that the user accessed the document and that a USB device existed.

However, the evidence does not prove:
1. The document was copied.
2. The USB device was involved.
3. Data was transferred.


### Conclusion

Additional investigation is required.

Possible artifacts:
1. Shellbags
2. LNK files
3. MFT timeline
4. USB connection history
5. File system timeline


#### Correlate artifacts

Strong conclusions require multiple independent sources of evidence.
