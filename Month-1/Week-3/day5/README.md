Regular Expressions Practice
📌 What I Learned Today

Today, I studied Regular Expressions (RegEx) — a powerful way to search, match, and manipulate text.
I explored:

How RegEx can act like a blueprint for searching patterns.

The role of metacharacters (e.g., [], {}, (), .*, |).

How grouping, quantifiers, and operators make searching more precise.

Using RegEx with the grep command in Linux.

🔑 Why This Practice Is Important

Configuration Audits: Many system files (like /etc/ssh/sshd_config) contain important security settings. RegEx helps us quickly analyze them.

Data Validation: Useful for checking structured inputs like emails, IPs, or passwords.

Efficiency: Instead of searching line by line, RegEx finds patterns instantly.

Security & Hacking Skills: In penetration testing and log analysis, RegEx is essential to filter sensitive information.

🛠 Practice Exercises (with /etc/ssh/sshd_config)
1) Show all lines that do not contain #
grep -v '#' /etc/ssh/sshd_config

2) Find all lines starting with Permit
grep -E 'Permit[A-Za-z0-9_-]*' /etc/ssh/sshd_config

3) Find all lines ending with Authentication
grep -E '\w*Authentication' /etc/ssh/sshd_config

4) Show all lines containing the word Key
grep -E 'Key' /etc/ssh/sshd_config

5) Lines beginning with Password and containing yes
grep -E '^Password.*yes' /etc/ssh/sshd_config

6) Lines ending with yes
grep -E 'yes$' /etc/ssh/sshd_config

📖 Key Takeaways

^ → Match start of line.

$ → Match end of line.

.* → Match anything in between.

| → OR operator.

-v → Invert match (exclude lines).

Practice on real config files helps understand both Linux administration and pattern matching.

👉 This practice not only improved my RegEx skills but also gave me insight into analyzing real configuration files that directly affect system security.
