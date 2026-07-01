## Day 6: Building an Investigation Timeline

#### Objective

Today's objective was to reconstruct an incident timeline using multiple forensic artifacts and write my first structured investigation report.

#### Evidence Provided

* Successful user logon
* File creation
* Prefetch execution evidence
* UserAssist execution evidence
* Registry Run Key
* Firewall outbound connection
* MFT deletion record

#### Timeline

| Time     | Event                                        |
| -------- | -------------------------------------------- |
| 09:00:15 | Successful logon by John                     |
| 09:02:11 | invoice.pdf.exe created                      |
| 09:03:04 | Prefetch recorded one execution              |
| 09:03:06 | UserAssist recorded execution activity       |
| 09:03:40 | Run Key created                              |
| 09:04:01 | Outbound HTTPS connection to 185.xxx.xxx.xxx |
| 09:15:23 | File deleted                                 |

#### Investigation Summary

The available evidence indicates that shortly after John logged in, an executable named `invoice.pdf.exe` appeared in the Downloads folder. Prefetch and UserAssist both contained evidence consistent with execution of the file. A Registry Run Key was subsequently created, suggesting persistence was established. Shortly afterward, an outbound HTTPS connection was observed, followed by deletion of the executable.

Although these artifacts establish a clear sequence of events, they do not determine the intent of the executable or confirm that the activity was malicious.

#### Lessons Learned

1. Timelines are built by combining multiple independent artifacts.
2. Every statement in a report should be supported by evidence.
3. Evidence and conclusions are not the same.
4. Multiple hypotheses should be considered before reaching a conclusion.
5. Uncertainty should be communicated clearly in forensic reporting.


#### Reflection

This was my first complete investigation report. The biggest lesson I learned was to distinguish between observations and interpretations. Rather than assuming intent, I focused on describing what the available evidence supported while clearly identifying the questions that remained unanswered. This approach strengthened both my investigative thinking and my report writing.
