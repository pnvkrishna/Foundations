# 🔐 Linux File Permissions — Teaching Script (PART 1)
---
## 🎯 1. Class Opening (Hook)

“Guys, today we are learning one of the most important topics in Linux — File Permissions.

Let me ask you one question…

👉 **If your system has no permissions, what happens?**

Anyone can:

* Read your data
* Modify your files
* Even destroy your system

So, permissions are the **first layer of security in Linux**.”

---

## 🧠 2. What are File Permissions?

“Linux is a **multi-user operating system**, meaning many users can access the same system.

To protect files, Linux uses:

* **Ownership**
* **Permissions**

👉 File permissions decide:

* Who can read a file
* Who can modify it
* Who can execute it”

---

## 👤 3. Ownership Concept

“Every file in Linux has 3 types of ownership:

* **User (u)** → Owner of the file
* **Group (g)** → Team or group of users
* **Others (o)** → Remaining users in the system

👉 Simple understanding:

* User → Creator of file
* Group → Team access
* Others → Everyone else”

---

## 🔑 4. Types of Permissions

“There are 3 types of permissions:

* **Read (r)** → View file content
* **Write (w)** → Modify the file
* **Execute (x)** → Run the file

👉 Real-life example:

* Read → Opening a book
* Write → Editing the book
* Execute → Running a program”

---

## 🔢 5. Why r = 4, w = 2, x = 1

“Now comes the important logic.

Linux internally uses **binary numbers (0 and 1)**.

We represent permissions like this:

r w x
1 0 0 → Read
0 1 0 → Write
0 0 1 → Execute

👉 Now convert to decimal:

* r = 4
* w = 2
* x = 1

👉 Think like switches:

* ON = 1
* OFF = 0”

---

## 🧮 6. Permission Combinations

“We combine values to form permissions:

* rwx → 4 + 2 + 1 = 7
* rw- → 4 + 2 = 6
* r-x → 4 + 1 = 5
* r-- → 4

👉 Example:

755 means:

* User → 7 → rwx
* Group → 5 → r-x
* Others → 5 → r-x”

---

## 📂 7. Understanding ls -l Output

“Let’s check permissions:

```bash
ls -l
```

Example output:

```bash
-rwxr-xr--
```

Break it:

* First part → file type
* Next 3 → user permissions
* Next 3 → group permissions
* Last 3 → others

👉 So:

* rwx → user
* r-x → group
* r-- → others”

---

## ⚙️ 8. chmod Command

“We use `chmod` to change permissions.”

### Symbolic Method:

```bash
chmod u+x file.sh
chmod g-w file.txt
chmod o+r file.txt
```

### Numeric Method:

```bash
chmod 755 file.sh
chmod 644 file.txt
```

👉 Numeric method is faster and used in real-world DevOps.

---

## 🔥 9. Cybersecurity Perspective

“This is very important.

❌ If you give:

```bash
chmod 777 file
```

👉 Anyone can:

* Read
* Modify
* Execute

This is a **huge security risk**.

👉 Best practices:

* Sensitive files → 600
* Scripts → 700 or 750
* Avoid 777 in production

👉 Real attack example:

If system files have write permission → attacker can modify them and gain access.”

---

## 🧠 10. UMASK Concept

“Umask defines **default permissions** for new files and directories.

👉 Formula:

Default Permission = Base Permission - Umask”

---

## 📊 11. Default Values

* File → 666
* Directory → 777

---

## 🧮 12. UMASK Example

“Let’s say:

```bash
umask 022
```

### For files:

666 - 022 = 644 → rw-r--r--

### For directories:

777 - 022 = 755 → rwxr-xr-x”

---

## 🔄 13. Another Example

```bash
umask 012
```

* File → 666 - 012 = 664
* Directory → 777 - 012 = 765

---

## ⚠️ Important Note

“Umask only affects **new files and directories**.

👉 It does NOT change existing files.”

---

## 🔐 14. UMASK in Cybersecurity

“Choosing correct umask is very important:

* 000 → ❌ Dangerous (full access)
* 022 → ✅ Standard
* 077 → 🔒 Highly secure (only owner access)”

---

## 🎯 15. Final Summary

“Let’s recap:

* Linux uses permissions for security
* 3 ownership types → user, group, others
* 3 permissions → read, write, execute
* r=4, w=2, x=1
* chmod → change permissions
* umask → controls default permissions

👉 If permissions are wrong → system can be hacked.”

---

## 🧠 Trainer Interaction Questions

Ask students:

1. What is permission for 755?
2. What happens if we use chmod 777?
3. If umask is 077, what will be file permission?

---

## 🚀 Closing Line

“Mastering permissions means mastering Linux security.

In next class, we will see advanced permissions like:
SUID, SGID, Sticky Bit — used in real-world hacking scenarios.”

---
