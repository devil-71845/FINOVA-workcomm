# Attack Surface 

## Explanation

In Bandit levels, the **attack surface** refers to all the commands, files, and system features that a user can interact with to obtain the password. Every accessible file, directory, permission setting, and available command increases the possible ways an attacker can explore the system.

For example, in Bandit, tools like `ls`, `find`, `grep`, `strings`, `base64`, and file permission checks are part of the attack surface. Even though direct access to password files is restricted, the presence of readable files, misconfigured permissions, or encoded data expands the attack surface.

As we progress through levels, we learn that reducing unnecessary access is important. The more files and commands exposed to a user, the easier it becomes to analyze patterns and locate sensitive information.

This shows that a larger attack surface increases the chances of exploitation. Good security practice focuses on minimizing the attack surface so that even if an attacker gains access, their options remain limited.
