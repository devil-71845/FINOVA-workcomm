# Passwords vs SSH Keys

Authentication is the process of proving identity to a system. Two of the most commonly used authentication mechanisms are passwords and SSH keys, but they differ significantly in how they work and how secure they are.

Passwords are based on something the user knows. A user enters a secret string, which is verified by the server. While simple and widely supported, passwords have several weaknesses. Users often reuse passwords, choose weak combinations, or fall victim to phishing attacks. Passwords can also be exposed through keyloggers, brute-force attacks, or database breaches. Even when hashed, poor password practices can still lead to compromise.

SSH keys use public-key cryptography and are based on something the user has. A key pair is generated: a private key remains securely on the client machine, while the public key is stored on the server. During authentication, the server challenges the client, and only the correct private key can produce a valid response. The private key is never transmitted, reducing the risk of interception.

SSH keys provide stronger security and are resistant to brute-force and phishing attacks. They are also well-suited for automation, making them ideal for cloud servers, DevOps pipelines, and remote administration.

In summary, passwords are easy to use but vulnerable to multiple attack vectors, while SSH keys offer a more secure and scalable authentication mechanism. For modern systems, SSH keys are generally the preferred choice.

# Data Transformation vs Data Protection

Data transformation and data protection are often confused, but they address entirely different objectives within a system.

Data transformation refers to modifying data into a different format or structure so it can be processed, stored, or transferred efficiently. Common examples include converting CSV files to JSON, normalizing database records, encoding data, or aggregating logs. Transformation improves compatibility and usability but does not inherently provide security.

Data protection focuses on safeguarding data from unauthorized access, alteration, or loss. This includes encryption, access control, authentication, backups, and data masking. The goal of data protection is to maintain confidentiality, integrity, and availability of information.

A frequent misconception is assuming that transformed data is secure. For instance, Base64 encoding changes how data appears but can be easily reversed. This is transformation, not protection. Encryption, in contrast, ensures that data remains unreadable without the appropriate key.

In simple terms, data transformation changes how data is represented, while data protection controls who can access data and how safely it is stored. Secure systems typically use both, but they serve distinct purposes.

# PATH Injection / PATH Hijacking

PATH injection, also known as PATH hijacking, is a security vulnerability that exploits how operating systems locate executable programs.

Operating systems use an environment variable called PATH to determine where to search for executables when a command is run. When a program executes a command without specifying its absolute path, the system searches through the directories listed in PATH and runs the first matching executable it finds.

The vulnerability arises when an attacker can influence the PATH variable or place a malicious executable in a directory that appears earlier in the PATH order. If a privileged program executes a command without an absolute path, the attacker’s malicious binary may be executed instead.

For example, if a script running with elevated privileges calls `ls` instead of `/bin/ls`, and the PATH contains a writable directory first, an attacker can place a fake `ls` binary there. The malicious program would then run with the script’s privileges.

PATH hijacking is particularly dangerous in SUID binaries, cron jobs, automation scripts, and system services. Prevention involves using absolute paths for system commands, sanitizing environment variables, and avoiding reliance on user-controlled PATH values.

In essence, PATH injection exploits misplaced trust in the execution environment, allowing attackers to redirect program execution to malicious code.
