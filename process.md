# 🔐 Process Management Master Class (Cybersecurity + DevOps)

---

# 🎯 CLASS OBJECTIVE

By the end of this class, students will:

* Understand what a **process** is
* Learn how Linux creates and manages processes
* Perform **process monitoring**
* Detect **malicious/suspicious processes**

---

# 🎤 1. OPENING SCRIPT (Say This)

“Guys, today we are learning one of the most important concepts in Linux and Cybersecurity — Process Management.

Whatever command you run… whatever application you open… everything becomes a process.

And attackers? They don’t show themselves directly… they hide as processes.

So if you understand processes… you can detect hackers.”

---

# 🧠 2. WHAT IS A PROCESS?

## ✅ Definition

A **process** is a **running instance of a program**

👉 Simple:
Program → Execution → Process

---

## 💻 DEMO

```bash
ls
```

👉 Explanation:

* Command executed
* Process created
* Output shown
* Process terminated

---

# 🧠 3. WHAT IS A PROGRAM?

## ✅ Definition

A **program** is an executable file stored on disk

## 💻 DEMO

```bash
which ls
```

👉 Output:

```
/usr/bin/ls
```

---

# 🔥 4. HOW PROCESS IS CREATED (CORE)

## 🧩 FLOW

```
User → Shell → Kernel → Process
```

---

## 🧠 STEP-BY-STEP

1. User enters command
2. Shell searches in `$PATH`
3. Shell calls:

   * `fork()` → creates child process
   * `exec()` → runs program
4. Kernel allocates CPU & memory
5. Process gets PID

---

## 📌 SYSTEM CALLS

| Call   | Purpose         |
| ------ | --------------- |
| fork() | Create process  |
| exec() | Execute program |
| wait() | Parent waits    |

---

# 🧠 5. PROCESS ID (PID)

## 💻 DEMO

```bash
echo $$
```

👉 Explanation:

* Every process has unique ID (PID)
* Used to track and control processes

---

# 🧠 6. PROCESS HIERARCHY

## 💻 DEMO

```bash
pstree
```

---

## 📌 KEY POINTS

* Parent → Child relationship
* systemd → PID = 1
* Kernel starts systemd

---

# 🧠 7. LINUX BOOT FLOW

```
BIOS → POST → MBR → GRUB2 → Kernel → systemd → Login → Shell
```

---

## 🔐 SECURITY NOTE

Attackers may target:

* Bootloader
* Kernel
* Services

---

# 🧠 8. FOREGROUND vs BACKGROUND

## 🔹 FOREGROUND

```bash
sleep 20
```

❌ Terminal blocked

---

## 🔹 BACKGROUND

```bash
sleep 20 &
```

✅ Terminal free

---

## 📊 DIFFERENCE

| Feature  | Foreground | Background |
| -------- | ---------- | ---------- |
| Input    | Keyboard   | No input   |
| Terminal | Blocked    | Free       |

---

# 🧠 9. JOB CONTROL

## 💻 DEMO

```bash
sleep 100
# Press Ctrl + Z
bg
jobs
fg
```

---

## 📌 COMMANDS

| Command  | Use        |
| -------- | ---------- |
| Ctrl + C | Kill       |
| Ctrl + Z | Suspend    |
| bg       | Background |
| fg       | Foreground |
| jobs     | List       |

---

# 🧠 10. PROCESS MONITORING

## 💻 COMMANDS

```bash
ps
ps -ef
ps aux
```

---

## 💻 FIND PROCESS

```bash
ps -ef | grep sshd
pgrep sshd
pidof sshd
```

---

## 💻 CHECK SHELL

```bash
echo $$
echo $PPID
```

---

# 🧠 11. REAL-TIME MONITORING

```bash
top
```

---

## 📊 SHOWS

* CPU usage
* Memory usage
* Running processes

---

# 🧠 12. HIGH RESOURCE PROCESSES

```bash
ps -e -o pid,%cpu,%mem,cmd --sort=-%cpu | head
```

---

# 🔥 13. CYBERSECURITY PERSPECTIVE

## 🧠 KEY IDEA

Hackers hide as processes

---

## 💻 DETECTION

```bash
ps aux
top
```

---

## 🚨 SUSPICIOUS SIGNS

* Unknown process
* High CPU usage
* Strange name
* Unknown path
* Weird parent process

---

# 🧪 14. REAL ATTACK SIMULATION LAB

## 🎯 SCENARIO: Fake Malware

### Step 1: Run attack

```bash
yes > /dev/null &
```

---

### Step 2: Detect

```bash
top
```

👉 Observe high CPU

---

### Step 3: Investigate

```bash
ps -ef | grep yes
```

---

### Step 4: Kill

```bash
kill -9 <PID>
```

---

## 🎤 EXPLANATION

“This is how a crypto miner behaves.

It silently consumes CPU.

If you don’t monitor processes, your system may already be compromised.”

---

# 🧪 15. STUDENT TASK

1. Run background process

```bash
sleep 200 &
```

2. Find PID

```bash
ps -ef | grep sleep
```

3. Bring to foreground

```bash
fg
```

4. Kill process

```bash
Ctrl + C
```

---

# 🧠 16. QUICK REVISION

* Process = running program
* Program = executable
* fork() → create
* exec() → execute
* PID → unique ID
* systemd → PID 1
* ps/top → monitoring

---

# 🚀 17. DEVOPS + CYBERSECURITY

* Monitor EC2 servers
* Detect abnormal processes
* Use:

  * CloudWatch
  * Prometheus
  * Grafana

---

# 🎤 FINAL CLOSING LINE

“If you understand processes, you understand Linux.

If you monitor processes, you can detect attackers.”

---
