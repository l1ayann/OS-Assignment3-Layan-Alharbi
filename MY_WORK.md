# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | layan al harbi |
| **Student ID** | 446051491 |
| **University Email** | 446051491@std.psau.edu.sa |
| **GitHub Username** | l1ayann |
| **Repository Link** | https://github.com/l1ayann/OS-Assignment3-Layan-Alharbi.git|
 
---

## 🎥 Video Link

**Video Link**: https://drive.google.com/drive/folders/1HBM3jyGy5m6CZPHkHJVDZxs4AqPsMhi8?usp=sharing

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 13, 2026, 9:30 AM]

**What I did**: Set up my GitHub repository and added my student ID.

**Details**:
- Forked the starter repository and renamed it.
- Added my student ID, `446051491`, to the Java file.
- Opened the project in VS Code and started checking the code.
- Made my first commit for the student ID change.

**Challenges**: At first, I needed some time to understand how the repository and Java file were organized.

**Solution**: I followed the instructions and checked the main classes before starting the features.

**Time spent**: Approximately 30 minutes.

---

### Entry 2 - [November 13, 2026, 10:00 AM]

**What I did**: Completed Feature 1 by protecting the ready queue.

**Details**:
- Added `ReentrantLock` to the `ReadyQueue` class.
- Protected `add()`, `poll()`, `processOf()`, and `snapshot()`.
- Used `try/finally` to make sure the lock is always released.
- Compiled and tested the program after making the changes.

**Challenges**: I was not sure where to put the lock and how to keep the existing methods working correctly.

**Solution**: I checked the methods one by one and added the lock around the shared queue operations.

**Time spent**: Approximately 1 hour.

---

### Entry 3 - [November 13, 2026, 11:00 AM]

**What I did**: Completed Feature 2 by protecting the shared statistics.

**Details**:
- Added `statsLock` inside the `SharedStats` class.
- Used one `ReentrantLock` for the three shared statistics.
- Protected the methods that update and read the statistics.
- Ran the program again to check the changes.

**Challenges**: I needed to understand why reading shared variables also requires protection.

**Solution**: I used the same lock for reading and updating the shared values to keep access synchronized.

**Time spent**: Approximately 1 hour.

---

### Entry 4 - [November 13, 2026, 12:00 PM]

**What I did**: Completed Feature 3 by replacing busy waiting with a semaphore.

**Details**:
- Added a counting `Semaphore` to the `ReadyQueue` class.
- Used `acquire()` to make CPUs wait when no process is available.
- Used `release()` when a process is added to the queue.
- Added `wakeUpAllCPUs()` so waiting CPUs can stop when all processes finish.
- Fixed duplicated lines while editing the code.

**Challenges**: I accidentally duplicated the semaphore declaration and the `add()` method. I also saw a red underline under `wakeUpAllCPUs()` before defining it.

**Solution**: I removed the duplicated lines and added the missing method inside `ReadyQueue`.

**Time spent**: Approximately 45 minutes.

---

### Entry 5 - [November 13, 2026, 12:45 PM]

**What I did**: Tested the completed program and checked the verification results.

**Details**:
- Compiled the Java file using `javac SchedulerSimulationSync.java`.
- Ran the program using `java SchedulerSimulationSync`.
- Checked the verification section in the output.
- The final run displayed `All shared values are consistent`.
- Reviewed the code for the three features.

**Challenges**: Earlier runs showed a red verification failure, which made me unsure whether my changes were correct.

**Solution**: I finished the remaining synchronization feature and ran the program again. The final verification passed.

**Time spent**: Approximately 20 minutes.

---

### Entry 6 - [Optional - Date and Time]

**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: Approximately 3 hours and 35 minutes.

**Most challenging part**: Feature 3 was the most challenging because I needed to understand how the semaphore works and how to wake up waiting CPUs correctly.

**Most interesting learning**: I learned how locks protect shared data and how semaphores allow CPUs to wait without busy waiting.

**What I would do differently next time**: I would review the code structure more carefully before adding new methods to avoid duplicated lines and errors.
---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

Through this assignment, I learned why synchronization is important when multiple threads work at the same time. I understood that a race condition can happen when two threads access and update the same shared variable. I used `ReentrantLock` to protect the ready queue and the shared statistics. I also learned that using `try/finally` helps make sure the lock is released after the critical section. In Feature 3, I used a counting semaphore to make CPUs wait when there were no available processes instead of continuously checking the queue. I noticed that the program worked correctly after applying the synchronization changes.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part for me was Feature 3 because I had to understand how the semaphore works with multiple CPUs. At first, I was confused about where to add `acquire()` and `release()`. I also had a problem with the `wakeUpAllCPUs()` method because it showed a red underline when I first called it. Another issue was that I accidentally duplicated some lines while editing the code. This made it difficult to know if the code structure was correct. I had to review the methods carefully before continuing.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I overcame the challenges by working on the assignment step by step instead of changing everything at once. I started with Feature 1, then moved to Feature 2, and finally completed Feature 3. When I faced an error, I checked the location of the code and reviewed the method structure. I also ran the program after making changes to see if the results were correct. When the final output displayed `All shared values are consistent`, I felt more confident about my solution. This approach helped me understand the features better.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization is used in many real-world applications where multiple users or processes access shared resources. For example, in banking applications, locks can help prevent two transactions from changing the same account balance at the same time. In ticket booking systems, synchronization can prevent two customers from booking the same seat. It is also useful in printers when several users send documents to the same printer queue. These examples are similar to my assignment because multiple CPUs access the same ready queue and shared statistics. Synchronization helps keep the data correct and prevents conflicts between threads.

### Optional: What would you like to learn more about?

I would like to learn more about deadlocks and how to prevent them when multiple threads use different locks.

### Optional: How confident do you feel about synchronization concepts now?

Intermediate. I understand the basic use of locks and semaphores, but I still need more practice with complex synchronization problems.

### Optional: Feedback on the assignment

The assignment was useful because it helped me understand synchronization through practical coding. Some parts were challenging at first, but testing the program helped me understand how the concepts work.

---
# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).
**Your Answer:** *(3-5 sentences)*

When I ran the original starter, the verification showed MISMATCH for context switches, total service time, and busy-waiting polls, while completed processes passed. A race condition can happen when CPU-1 reads `contextSwitchCount`, then `RaceWindow.pause()` allows CPU-2 to read the same value before CPU-1 updates it. Both CPUs may write the same updated value, causing one increment to be lost. This problem can also happen without `RaceWindow.pause()` because the operating system can switch between threads at any time. It is difficult to detect because the results can change between runs.

Verification block of the **original starter**:
```
Context switches: MISMATCH
Completed processes: PASS
Total service time: MISMATCH
Busy-waiting polls: MISMATCH

At least one check failed:
a race condition or busy waiting is still present.
```

Verification block of **my final version**:
```
Context switches (quanta executed)  expected 37       observed 37       PASS
Completed processes                 expected 20       observed 20       PASS
Total service time (ms)             expected 144366   observed 144366   PASS
Busy-waiting polls (must be 0)      expected 0        observed 0        PASS

All shared values are consistent.
```

**Explanation of the timeline:**

For example, CPU-1 reads `contextSwitchCount` = 12. Before CPU-1 updates it, CPU-2 also reads 12. CPU-1 writes 13, then CPU-2 writes 13. The correct value should be 14, but the result is 13 because one update was lost.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I used `queueLock` to protect the ready queue and `statsLock` to protect the three shared statistics: `contextSwitchCount`, `completedProcessCount`, and `totalServiceTime`. I chose one lock for the statistics because it is easier to manage, although updates may need to wait for each other. The ready queue uses a different lock to avoid unnecessary blocking between queue operations and statistics updates. Using `ReentrantLock` with `try/finally` provides mutual exclusion and allows other threads to make progress after the lock is released. However, the default `ReentrantLock` is not fair, so bounded waiting is not guaranteed.


| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()` | `queueLock` | Protects adding processes to the shared queue. |
| `ReadyQueue.poll()` | `queueLock` | Prevents multiple CPUs from removing the same process. |
| `ReadyQueue.processOf()` | `queueLock` | Protects access to the shared map. |
| `ReadyQueue.snapshot()` | `queueLock` | Protects reading the queue contents. |
| `incrementContextSwitch()` | `statsLock` | Prevents lost updates. |
| `incrementCompletedProcess()` | `statsLock` | Protects the completed process counter. |
| `addServiceTime()` | `statsLock` | Protects the total service time. |
| Statistics getter methods | `statsLock` | Protects reading shared statistics. |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.


**Your Answer:** *(3-5 sentences)*

In the original starter, CPUs used busy waiting by repeatedly checking the ready queue when it was empty, which wasted CPU time. The original output showed a MISMATCH for `Busy-waiting polls` (expected 0), while my final version showed 0 and passed the check. In my solution, the counting semaphore starts at 0 because the queue is initially empty, and its permits represent available processes. After the initial `numProcesses` additions, the semaphore has `numProcesses` permits before any CPU acquires them. When all processes are completed, the last CPU calls `release(totalCPUs)` to wake up waiting CPUs; otherwise, some CPUs could remain blocked forever.
## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
This assignment is similar to the classical Producer-Consumer problem. The main thread acts as a producer when it adds the initial processes, while the CPUs act as consumers when they take processes from the ready queue. The CPUs can also act as producers when they add unfinished processes back to the queue


**Semaphores for a bounded queue (name and initial value)**:

empty = K: Represents the available empty spaces in the queue.
full = 0: Represents the number of available processes.
mutex = 1: Protects the shared queue.
  
**Deadlock scenario and prevention**:
A deadlock could happen if a producer holds the mutex while waiting for an empty slot. The consumer cannot access the queue to remove a process because the mutex is already locked. To prevent this, the producer should wait for an empty slot before acquiring the mutex. This breaks the hold-and-wait condition.

## Summary

**Key concepts I understood through these questions:**
1. Understanding how `ReentrantLock` protects shared data and prevents race conditions.
2. Learning how a counting semaphore controls access to shared resources between threads.
3. Understanding the Producer-Consumer problem and how it relates to CPU scheduling.

**Concepts I need to study more:**
1. Deadlocks and the four necessary conditions.
2. Using locks and semaphores in more complex programs.
---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
