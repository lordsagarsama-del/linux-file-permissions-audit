# Linux File Permissions & Access Control Audit

## 📌 Project Overview
In this security assignment, I investigated and updated file permissions for an organization's research team to ensure data security and enforce the **principle of least privilege**[cite: 21]. 

## 🛠️ Tools & Environment
* Linux Command Line (Bash)
* Terminal utilities (`ls`, `chmod`)

## 🔍 Investigation & Actions Taken

1. **Auditing Existing Permissions:**
   Navigated to the project directory and executed `ls -la` to inspect 10-character permission strings[cite: 22]. Found that a project file (`project_k.txt`) had public write permissions (`-rw-rw-rw-`), violating organizational security standards[cite: 23, 24].

2. **Remediating Public Write Access:**
   Executed the command to remove public write privileges[cite: 24]:
   \`\`\`bash
   chmod o-w project_k.txt
   \`\`\`
   Verified the update via long listing (`-rw-rw-r--`), ensuring proper access restrictions[cite: 24].

3. **Securing Hidden Archive Files:**
   Restricted an archived hidden file (`.project_x.txt`) to read-only status for the owner and group[cite: 24]:
   \`\`\`bash
   chmod 440 .project_x.txt
   \`\`\`

4. **Isolating Confidential Directories:**
   Secured the sensitive `drafts` directory so only the owner (`researcher2`) can access it, blocking all group and public access[cite: 25]:
   \`\`\`bash
   chmod 700 drafts
   \`\`\`

## 🚀 Business Impact
By systematically applying targeted `chmod` commands, I removed unauthorized write risks, protected confidential drafts, and ensured compliance with foundational access control policies[cite: 26].
