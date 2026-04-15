Perfect 🔥
Now we move to **Part 2 — Commands Mastery (Real Power Begins Here)**

👉 This is where students feel: **“I can actually use Linux”**

---

# 📘 Disk Management — Part 2 (COMMANDS + REAL ANALYSIS 💯)

---

# 🎯 SESSION OBJECTIVE

👉 “By end of this class, you will:

* Check disk space confidently
* Identify storage problems
* Find which folder is consuming space
* Think like a troubleshooting engineer”

---

# 🎬 1. HOOK (START WITH PROBLEM)

### 🎙️ Speak:

“Imagine…

Your company website suddenly goes down.

You check server…

CPU is fine
Memory is fine

👉 Then what could be the problem?”

(wait…)

👉 “Disk full.”

---

### 💡 Impact Line

👉 “Today we learn how to detect that in seconds”

---

# 🧠 2. COMMAND 1 — `df` (BIG PICTURE 🔥)

---

## ✅ What is `df`?

👉 “df shows **overall disk space usage**”

---

## 💻 Demo

```bash
df -h
```

---

## 🎙️ How to Explain Output

Show columns:

* Size → Total disk
* Used → Used space
* Avail → Free space
* Use% → Important 🔥
* Mounted on → Location

---

## 🎯 Focus Students Here

👉 “Always focus on `/` (root)”

---

## 📊 Real Interpretation Example

👉 “If Use% is:

* 50% → Safe ✅
* 70% → Warning ⚠️
* 90%+ → Danger 🚨”

---

## 💡 Teaching Line

👉 “df tells WHAT is happening”

---

---

# 🧠 3. COMMAND 2 — `du` (DEEP ANALYSIS 🔍)

---

## ✅ What is `du`?

👉 “du shows which file/folder is using space”

---

## 💻 Demo

```bash
du -sh *
```

---

## 🎙️ Explain

* `du` → disk usage
* `-s` → summary
* `-h` → human readable

---

## 📊 Real Use

👉 “df shows disk is full…

But du tells WHO is responsible”

---

## 💡 Teaching Line

👉 “df shows problem
du finds culprit”

---

---

# 🧪 4. STEP-BY-STEP TROUBLESHOOTING FLOW (VERY IMPORTANT 🔥)

Write on board:

```text
Step 1 → df -h   (Check disk)
Step 2 → cd /var or /home
Step 3 → du -sh *  (Find large folders)
```

---

### 🎙️ Explain Like Story

“First we detect problem
Then we investigate
Then we find root cause”

---

---

# 💻 5. REAL DEMO FLOW (DO LIVE)

---

## Step 1:

```bash
df -h
```

👉 “Check if disk is full”

---

## Step 2:

```bash
cd /var
```

👉 “Logs usually here”

---

## Step 3:

```bash
du -sh *
```

👉 “Find biggest folder”

---

## Step 4 (Optional):

```bash
cd log
du -sh *
```

---

### 🎯 Teaching Line

👉 “Keep going deeper until you find problem”

---

---

# 🔥 6. ADVANCED (BUT SIMPLE) — FIND TOP FILES

---

## 💻 Demo

```bash
du -ah | sort -nr | head -10
```

---

### 🎙️ Explain Simply

👉 “This shows top 10 largest files”

---

### 💡 Use Case

👉 “Very useful in real production issues”

---

---

# 🔐 7. SECURITY CONNECTION (MAKE STRONG IMPACT)

---

### 🎙️ Speak:

“In cybersecurity…

Logs are very important”

---

👉 If disk full:

* Logs stop writing ❌
* Attacks not recorded ❌
* Monitoring fails ❌

---

### 🚨 Attack Scenario

“Attacker fills disk → system blind”

---

### 💡 Final Line

👉 “Disk monitoring = security responsibility”

---

---

# ⚠️ 8. COMMON MISTAKES

---

❌ Using only `df`
❌ Not checking `/var/log`
❌ Ignoring large hidden files
❌ Panic without checking properly

---

---

# 🧠 9. MEMORY FRAMEWORK (VERY IMPORTANT)

Write:

👉 **df → du → dig deeper**

---

Explain:

* df → detect
* du → investigate
* dig → find root cause

---

---

# 🔁 10. FINAL REVISION (END STRONG)

### 🎙️ Speak:

“Today you learned real skill:

👉 How to check disk
👉 How to find problem
👉 How to troubleshoot like engineer

This is not theory — this is real-world skill”

---

---

# 🧪 11. STUDENT TASK (MANDATORY)

---

### Task 1:

* Run `df -h`
* Identify main disk

---

### Task 2:

* Go to `/home`
* Run `du -sh *`

---

### Task 3:

* Find largest folder

---

### 🔥 Challenge Task

👉 “Find top 5 largest files in your system”

---

---

# 🏁 FINAL NOTE FOR YOU

👉 This part is:

* Practical
* Powerful
* Real-world ready

👉 Students will feel:
“I can troubleshoot now”

---

# 🚀 NEXT STEP

We go to:

👉 **Part 3 — Mounting + Real Disk Control (mkfs, mount basics)**

This is where students feel like **real system admins**

---

Just say: **next** 🔥
