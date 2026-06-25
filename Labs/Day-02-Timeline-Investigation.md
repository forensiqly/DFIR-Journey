## Day 02 - Timeline Investigation

### Objective

Learn how forensic investigators use timestamps and multiple artifacts to build timelines and reconstruct events.


### Topics Covered

#### File Timestamps

Studied the three primary file timestamps:

1. Created
2. Modified
3. Accessed

Created a test file and observed how timestamps changed after modifying the file.

#### Findings

Initial timestamps:

1. Created: 25/06/2026 09:31:43
2. Modified: 25/06/2026 09:31:43

After editing the file:

1. Created timestamp remained unchanged.
2. Modified timestamp changed to 25/06/2026 09:35:36.

Conclusion:

The Modified timestamp records changes to file content, while the Created timestamp remains unchanged when editing an existing file.


#### File Rename Experiment

Created a file named:

secret.txt

Renamed it to:

important.txt

Findings:

1. Created timestamp did not change.
2. Modified timestamp did not change.

Conclusion:

Renaming a file does not necessarily modify the file contents. Therefore, the Modified timestamp remained unchanged.


### NTFS Concepts Learned

#### NTFS

New Technology File System (NTFS) is the default file system used by Windows.

NTFS stores:

1. Files
2. Folders
3. Permissions
4. Metadata
5. Timestamps

#### Master File Table (MFT)

The MFT acts as a database containing records of files stored on the system.

Forensic Value:

1. Helps identify files that existed on a system.
2. May retain evidence even after files are deleted.
3. Provides metadata useful during investigations.


### Timeline Analysis Exercise

#### Evidence Observed

09:00 User logon

09:05 invoice.pdf.exe created

09:06 Run Key created

09:07 Process executed

09:08 Network connection established

09:20 invoice.pdf.exe deleted


### Analysis

A file named invoice.pdf.exe was created shortly after a successful user logon.

A Run Key was then created, indicating persistence was established.

The file was executed and subsequently initiated a network connection.

The executable was later deleted.

The evidence suggests activity occurred between execution and deletion, but additional evidence would be required to determine the nature of that activity.


### Key Questions Raised

1. Who created the file?
2. What was the purpose of the executable?
3. Which process was executed?
4. What occurred during the network connection?
5. What happened between 09:08 and 09:20?
6. Was the activity malicious?


### Lessons Learned

1. Timestamps help reconstruct events.
2. Deleted files may still leave recoverable evidence.
3. Investigations rely on multiple artifacts rather than a single source of evidence.
4. Analysts should distinguish between evidence and assumptions.
5. Timelines help identify gaps that require further investigation.


### Skills Practiced

1. File timestamp analysis
2. Evidence collection
3. Timeline creation
4. Hypothesis development
5. Investigative questioning


### Reflection

Today I learned that forensic investigations are not about finding immediate answers. They are about collecting evidence, building timelines, identifying gaps in the evidence and asking the right questions.

One of the most important lessons was understanding the difference between evidence and conclusions. A timeline can suggest what happened, but additional evidence is required before making definitive claims.

I also learned that deleted files are not necessarily gone. Artifacts such as timestamps, metadata and file system records may still provide valuable evidence during an investigation.

The most important question I asked today was:

"What happened between execution and deletion?"

This showed me that the most important part of an investigation is often hidden in the gaps between known events.
