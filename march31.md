# 🚀 Day 3: Linux File System (Cybersecurity Focus)

---

## 🎯 Objective

By the end of this class, students should:

* Understand Linux file system structure
* Know purpose of key directories
* Connect file system to cybersecurity
* Navigate real system confidently

---

# 🔥 1. Powerful Opening (2–5 mins)

👉 Say:

“If your server gets hacked at 2 AM… what will you do?”

Pause.

👉 Ask:

* Where are logs stored?
* Where are configuration files?
* Where is user data?

👉 Then say:

“If you don’t know Linux file system… you cannot investigate an attack.”

---

# 💥 2. Problem Statement (Create Need)

👉 Say:

“If Linux stores everything in one place…”

* No organization
* No security
* No debugging

👉 Strong line:

“Chaos means no control.”

---

# 📁 3. Concept: What is File System?

👉 Definition:

“File system is how Linux organizes and stores data.”

👉 Key Idea:

“In Linux, everything is a file”

Examples:

* Logs → file
* Config → file
* Devices → file

---

# 🏦 4. Bank Analogy (Core Understanding)

👉 Say:

“In a bank…”

* Money → locker room
* Documents → records room
* Logs → CCTV
* Manager → admin room

👉 Ask:

“Can a bank keep everything in one room?”

❌ No

👉 Then:

“Linux also organizes everything based on purpose.”

---

# 📊 5. Mapping: Bank vs Linux

| 🏦 Bank        | 💻 Linux   | Purpose        |
| -------------- | ---------- | -------------- |
| Main building  | `/`        | Starting point |
| Locker room    | `/home`    | User files     |
| Manager room   | `/root`    | Admin files    |
| Rules room     | `/etc`     | Configuration  |
| CCTV logs      | `/var/log` | Logs           |
| Temporary desk | `/tmp`     | Temp files     |

---

|    Bank    |  Purpose          | 
|------------| ------------------|
| Main Building | Starting point |
| Locker room   | user files     |
| manager room  | admin files    | 
| control room  | controls system | 
| cctv logs     | tracking        |  
| Temporary desk | temparary files |
| power supply   | start up       | 


---

# 🧠 6. Root Directory (`/`)

👉 Say:

“`/` is the starting point of Linux”

👉 Analogy:

“Like main building of a bank”

👉 Key:

“All directories come from `/`”

---

# ⚙️ 7. Important Directories (Explain Clearly)

---

## 🏠 `/home`

* User files
* Personal data

👉 Line:
“Each user has their own space”

---

## ⚙️ `/etc`

* Configuration files
* System behavior

👉 Line:
“If `/etc` changes… system behavior changes”

---

## 📜 `/var/log`

* Logs
* System activity

👉 Cyber Line:
“If logs are gone… attacker is invisible”

---

## 👑 `/root`

* Admin home
* High privilege

---

## 🧪 `/tmp`

* Temporary files
* Auto-cleaned

👉 Cyber:
“Attackers may use temp space”

---

## 🚀 `/boot`

* Boot files
* Kernel

👉 Connect:
“System starts from here”

---

## 🧠 `/proc`

* System info (virtual)

👉 Demo:

```bash
cat /proc/cpuinfo
```

---

# 💻 8. Live Demo (VERY IMPORTANT)

Run:

```bash
cd /
ls
```

👉 Ask:

“Do you understand these folders?”

---

Run:

```bash
cd /var/log
ls
```

👉 Say:

“These are real logs — used in debugging and security”

---

# 🧪 9. Student Lab

👉 Tasks:

1. Go to `/home`
2. Create a file
3. Move to `/tmp`
4. Delete it

👉 Challenge:

“Find where logs are stored”

---

# ⚔️ 10. Cybersecurity Connection

👉 Explain:

* Logs → detect attacks
* Config → system control
* User files → sensitive data

👉 Strong Lines:

“Attackers don’t guess — they target”

“If you don’t know file system… you cannot secure system”

---

# ❌ 11. Failure Scenarios

👉 Ask:

* What if `/var/log` is deleted?
* What if `/etc` is modified?

👉 Answer:

* No logs → no debugging
* Config change → system compromised

---

# 🧠 12. Mental Model

👉 Repeat:

“Everything is a file”

“Linux is structured — not random”

---

# 🎯 13. Recap Questions

Ask students:

* What is `/`?
* Where are logs stored?
* Where are config files?
* Where is user data?

👉 Make one student explain

---

# 🧑‍🏫 14. Communication Training

### 10 sec:

“Linux file system organizes data using directories starting from root”

---

### 30 sec:

Explain `/home`, `/etc`, `/var`

---

### 2 min:

Explain using bank analogy

---

# 🔥 15. Final Impact Line

👉 “Linux is structured for control, security, and efficiency”

👉 “If you understand structure… you control the system”

👉 “If you don’t… you are just using it blindly”

---

# 🚀 End Goal

Students should feel:

✔ This is important
✔ I can explore system
✔ I understand structure
✔ Linux is required for cybersecurity

---
