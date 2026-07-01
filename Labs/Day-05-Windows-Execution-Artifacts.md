## Day 5: Windows Execution Artifacts

#### Objective

Today's objective was to understand Windows execution artifacts and how they help investigators determine whether a program may have been executed. I also learned why no single artifact should be trusted in isolation.

#### Topics Covered

* UserAssist
* Execution artifacts
* ROT13 encoding
* Registry values
* Artifact correlation
* Investigation principles

#### Practical Exercise

I explored the UserAssist Registry key:
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\UserAssist

##### Observations

1. The UserAssist key existed on my system.
2. Multiple GUID folders were present.
3. Each GUID contained a **Count** subkey.
4. One Count key contained approximately 128 entries.
5. The value names appeared encoded.
6. The entries also contained binary data and numerical information.

During the exercise, I learned that:

1. The encoded names use ROT13.
2. The binary data stores execution related metadata.
3. The Count key contains Registry values representing recorded application activity.

#### Key Lessons Learned

1. UserAssist records evidence consistent with user initiated program execution through Windows Explorer.
2. Execution artifacts should be interpreted together rather than individually.
3. Multiple GUIDs exist because Windows organizes different categories of UserAssist data separately.
4. Registry value names are ROT13 encoded, while the binary data itself is not.

#### Investigation Thinking

Given a scenario where a suspicious executable was created and later deleted, I concluded that:

1. Prefetch may contain evidence of execution.
2. UserAssist may also contain evidence of execution.
3. No single artifact is sufficient to prove what happened.
4. Multiple independent artifacts should be correlated before reaching conclusions.
5. Missing artifacts do not prove that execution never occurred.

#### Reflection

Today's lesson changed how I think about execution artifacts. Instead of asking whether one artifact proves execution, I learned to ask what each artifact contributes to the overall story. This shift in thinking reinforced the importance of evidence correlation and careful reporting.
