## Day 3: Windows User Activity Artifacts (Prefetch, Recent Items & Jump Lists)
### Objective

Today's goal was to understand how Windows records user activity through forensic artifacts and how investigators use multiple artifacts together to reconstruct events instead of relying on a single source of evidence.

### Topics Covered
#### 1. Windows Prefetch

Learned that Windows uses Prefetch to improve application startup performance while also leaving valuable forensic evidence.

Key concepts learned:

- What Prefetch is
- Location of Prefetch (C:\Windows\Prefetch)
- .pf files
- How Prefetch helps determine whether an application was executed
- Why investigators should corroborate Prefetch with other artifacts

### Practical Exercise

Explored the Prefetch directory.

Observations:

1. Approximately 502 Prefetch files were present.
2. Recognized all major applications that had been executed.
3. Investigated the ReadyBoot folder and learned that it stores boot optimization traces rather than application execution data.
4. Observed ReadyBoot trace files being updated immediately after a Windows restart, demonstrating the importance of correlating timestamps with known system activity.

### Experiment

Examined the OBSIDIAN.EXE Prefetch file.

Initial observation:

- The modified timestamp matched the application's installation date.

Hypothesis:

- I expected the timestamp to update while the application was in use.

Experiment:

- Closed Obsidian completely.
- Waited briefly.
- Reopened the application.
- Rechecked the Prefetch file.

Result:

- The Prefetch timestamp updated after the application was executed again.

Lesson learned:

- Running software continuously is different from executing it again.
- Assumptions should always be tested through observation.


#### 2. Recent Items

Explored Windows Recent Items using:

*shell:recent*

Observations:

- Approximately 150 recent items.
- File types included PDF, JPG, PNG and MP4.
- Recognized every file.
- The recorded dates matched my recent activity.

Key takeaway:

Recent Items provide evidence of recently accessed files but do not necessarily prove user intent or actions beyond access.

#### 3. Jump Lists

Learned that Jump Lists provide additional evidence of files and folders recently accessed through specific applications.

Key takeaway:

Jump Lists complement Prefetch and Recent Items by providing another source of user activity evidence.

### Investigation Exercise

#### Evidence Observed
09:00 User logon
09:03 Microsoft Word Prefetch updated
09:04 Confidential.docx appeared in Recent Items
09:05 Microsoft Word Jump List referenced Confidential.docx
09:07 USB device connected

#### Analysis

The available evidence suggests Microsoft Word was executed shortly after user logon. Both Recent Items and the Microsoft Word Jump List referenced Confidential.docx, indicating the document was accessed during the session.

Although a USB device was connected, the available evidence does not prove that the document was copied to the device.

Additional artifacts would be required to determine whether any files were transferred.

### Conclusion

The evidence supports document access but does not support a conclusion that data theft occurred.

Further investigation would require additional artifacts such as USB registry artifacts, Event Logs, Shortcut (.lnk) files and file system metadata.

##### Confidence Level: *Medium*

#### Key Lessons
1. Prefetch indicates application execution.
2. Recent Items record recently accessed files.
3. Jump Lists provide additional evidence of user activity.
4. A single artifact should never be used as the sole basis for a forensic conclusion.
5. Correlating multiple independent artifacts produces stronger findings.
6. Investigation should focus on evidence rather than assumptions.
7. When evidence is insufficient, the correct conclusion is often: "Further investigation is required."

### Reflection
Today reinforced the importance of validating assumptions through experimentation. I initially believed a Prefetch file's modified timestamp would update while an application was actively in use. After designing and performing a simple experiment by closing and reopening Obsidian, I observed that the timestamp updated only after a new execution. This reminded me that forensic conclusions should be based on tested evidence rather than intuition. I also learned that correlating Prefetch, Recent Items, and Jump Lists provides a much stronger understanding of user activity than relying on any single artifact alone.
