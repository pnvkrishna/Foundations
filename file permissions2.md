# 🔐 Linux Advanced Permissions — Teaching Script (PART 2)

---

## 🎯 1. Opening Hook (Create Curiosity)

“Till now, we learned basic permissions.

But let me ask you…

👉 Can a normal user execute a command as root?

👉 Can multiple users safely share a directory?

👉 Can we prevent users from deleting each other's files?

👉 YES — using Advanced Permissions.”

---

# 🔥 2. Introduction to Advanced Permissions

“There are 3 special permissions in Linux:

* **SUID (Set User ID)** → 4
* **SGID (Set Group ID)** → 2
* **Sticky Bit** → 1

👉 These are called **special permission bits**.”

---

# 👑 3. SUID (Set User ID)

## 🧠 Concept

“SUID allows a user to execute a file with the **owner’s permissions**, not their own.”

---

## 🎯 Example

```bash
ls -l /usr/bin/passwd
```

👉 Output:

```bash
-rwsr-xr-x
```

👉 Notice `s` in place of `x`

---

## 💡 Explanation

“When a normal user runs `passwd`,
it updates `/etc/shadow` (a root-owned file).

👉 Without SUID → access denied
👉 With SUID → runs as root”

---

## ⚙️ How to Set

```bash
chmod u+s file
```

---

## 🔥 Cybersecurity Angle

“If SUID is set on wrong files:

👉 attacker can gain root access

Example:

* SUID on shell → privilege escalation ❌”

---

## 🚨 Real Attack Concept

“If `/bin/bash` has SUID:

```bash
chmod u+s /bin/bash
```

👉 Any user can become root”

---

---

# 👥 4. SGID (Set Group ID)

## 🧠 Concept

“SGID has 2 uses:

1. On files → run with group privileges
2. On directories → inherit group ownership”

---

## 🎯 Directory Example (Important)

```bash
mkdir /project
chown root:devteam /project
chmod 2775 /project
```

👉 Now:

* Any file created inside → inherits `devteam` group

---

## 💡 Without SGID

* File owner = user
* Group = user’s default group ❌

## 💡 With SGID

* Group = parent directory group ✅

---

## 🔥 Cybersecurity Angle

“Prevents permission mismatch in shared directories”

---

---

# 📌 5. Sticky Bit

## 🧠 Concept

“Sticky bit ensures:

👉 Only owner can delete their files”

---

## 🎯 Example

```bash
ls -ld /tmp
```

👉 Output:

```bash
drwxrwxrwt
```

👉 `t` → sticky bit

---

## 💡 Explanation

“In `/tmp`:

* Everyone can create files
* But cannot delete others’ files”

---

## ⚙️ Set Sticky Bit

```bash
chmod +t directory
```

---

## 🔥 Cybersecurity Angle

“Prevents users from deleting or tampering with others' files”

---

---

# 🧮 6. Special Permission Numbers

| Permission | Value |
| ---------- | ----- |
| SUID       | 4     |
| SGID       | 2     |
| Sticky     | 1     |

---

## 🎯 Example

```bash
chmod 4755 file
```

👉 4 → SUID
👉 755 → normal permissions

---

# 🔐 7. ACL (Access Control List)

## 🧠 Why ACL?

“Normal permissions allow only:

* 1 user
* 1 group

👉 What if multiple users need access?”

---

## 🎯 Solution → ACL

---

## ⚙️ Commands

### Set ACL for user:

```bash
setfacl -m u:john:rwx file
```

### Set ACL for group:

```bash
setfacl -m g:dev:r-x file
```

---

## 🔍 View ACL

```bash
getfacl file
```

---

## ❌ Remove ACL

```bash
setfacl -x u:john file
setfacl -b file
```

---

## 🔥 Cybersecurity Angle

“ACL gives fine-grained control
But misconfiguration → data leakage”

---

---

# 🔒 8. File Attributes (chattr)

## 🧠 Concept

“Attributes control file behavior beyond permissions”

---

## ⚙️ Commands

```bash
chattr +i file   # immutable
chattr +a file   # append only
lsattr file
```

---

## 💡 Important Attributes

### 🔹 Immutable (`+i`)

* Cannot modify
* Cannot delete
* Even root cannot change

👉 Used for:

* Protect config files

---

### 🔹 Append Only (`+a`)

* Only append data
* Cannot delete or modify existing content

👉 Used for:

* Logs

---

## 🔥 Cybersecurity Angle

“Even if attacker gets root:

👉 cannot modify immutable files”

---

---

# 🚀 9. Real-World Scenarios

### Scenario 1: Shared DevOps Directory

* Use SGID → group inheritance
* Use umask 002 → collaboration

---

### Scenario 2: Secure Config Files

* chmod 600
* chattr +i

---

### Scenario 3: Public Directory (/tmp)

* chmod 1777
* Sticky bit enabled

---

---

# 🎯 10. Interview Questions

👉 What is SUID?
👉 Difference between SGID on file vs directory?
👉 Why sticky bit is used in /tmp?
👉 What is ACL?
👉 Difference between chmod and chattr?

---

# 🧠 11. Final Summary

* SUID → run as owner
* SGID → group inheritance
* Sticky → protect files
* ACL → fine-grained permissions
* chattr → extra protection

👉 Permissions = Security Foundation in Linux

---

# 🚀 Closing Line

“If you understand permissions deeply,
you can both **secure systems** and **break misconfigured systems**.”

---
