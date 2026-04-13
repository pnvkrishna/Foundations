# 🎤 Module 2: Users, Permissions & Privilege Escalation (Cybersecurity Focus)

---

## 🟢 Opening (First 10 mins)

“Yesterday we learned Linux basics.
Today we are entering the *real cybersecurity zone*.

Let me ask you one question…
If a hacker gets access to a system as a normal user…
how does he become ROOT?

That secret is hidden in **users and permissions**.
If you understand this — you can both attack and defend a system.”

---

## 🔵 Part 1: Users & Groups (30 mins)

### Concept:

* Linux is a **multi-user system**
* Each user has:

  * UID (User ID)
  * GID (Group ID)

### Commands:

```bash
whoami
id
```

### Explain:

* `whoami` → current user
* `id` → user identity (UID, GID, groups)

---

### User Data Files:

```bash
cat /etc/passwd
cat /etc/shadow
```

### Explanation:

* `/etc/passwd` → list of users (public)
* `/etc/shadow` → password hashes (restricted)

💣 Cyber Note:

> If attacker reads `/etc/shadow` → system compromised

---

### Task:

* Find your UID
* Count number of users in system

---

## 🔵 Part 2: File Permissions (Core – 60 mins)

### Command:

```bash
ls -l
```

Example:

```
-rwxr-xr--
```

### Breakdown:

* 1st → File type
* Next 3 → Owner
* Next 3 → Group
* Last 3 → Others

---

### Permissions:

| Symbol | Meaning |
| ------ | ------- |
| r      | read    |
| w      | write   |
| x      | execute |

---

### Numeric Permissions:

```bash
chmod 777 file
chmod 755 file
chmod 600 file
```

| Number | Meaning |
| ------ | ------- |
| 7      | rwx     |
| 6      | rw-     |
| 5      | r-x     |

---

💣 Cyber Note:

> 777 = anyone can modify → malware risk

---

### Demo:

```bash
touch demo.sh
chmod 777 demo.sh
```

Ask:

* Is this secure? ❌

---

### Task:

* Create a file
* Apply:

  * 777
  * 755
  * 600
* Observe differences

---

## 🔵 Part 3: Ownership (20 mins)

### Commands:

```bash
ls -l
chown user file
chgrp group file
```

### Explanation:

* Owner controls file
* Wrong ownership = security risk

---

## 🔴 Part 4: Special Permissions (40 mins)

### 🔥 SUID (Set User ID)

```bash
ls -l /bin/passwd
```

* Look for `s` in permissions

💡 Meaning:

> File runs as owner (usually root)

---

### Find SUID Files:

```bash
find / -perm -4000 2>/dev/null
```

💣 Cyber Note:

> Vulnerable SUID = root access

---

### 🔥 Sticky Bit

```bash
ls -ld /tmp
```

💡 Meaning:

> Only file owner can delete files (even in shared folder)

---

## 🔴 Part 5: Privilege Escalation (30 mins)

### Command:

```bash
sudo -l
```

### Explanation:

* Shows what commands user can run as root

---

### Example Attack:

```bash
sudo vim
```

Inside vim → escape to shell → ROOT access

💣 Concept:

> This is called **Privilege Escalation**

---

## 🧪 Final Hands-on (30 mins)

“You are attacker. Find vulnerabilities.”

### Commands:

```bash
find / -perm -4000 2>/dev/null
sudo -l
ls -l
```

### Task:

* Identify:

  * SUID files
  * Weak permissions
  * Misconfigurations

---

## 🎯 Interview Questions

1. Difference between `/etc/passwd` and `/etc/shadow`
2. What is 777 risk?
3. What is SUID?
4. How to find SUID files?
5. What is privilege escalation?

---

## 🧠 Closing

“Today you didn’t just learn Linux…
you learned how systems get hacked.

From now… whenever you see permissions…
think like a hacker.”

---

## 🔥 Golden Line

“Security is not about tools…
it is about understanding mistakes.”
