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
| **Full Name** | Mohammed rashid aldrees |
| **Student ID** | 444052517 |
| **University Email** | 444052517@std.psau.edu.sa |
| **GitHub Username** | mohammedaldres |
| **Repository Link** | https://github.com/mohammedaldres/OS-Assignment3-Mohemmed-Aldrees |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

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

### Entry 1 - [Date and Time]
**What I did**: Forked the starter repository, set my student ID, and ran the broken starter code

**Details**:
- Forked the repository under my GitHub account `mohammedaldres` and made sure its visibility is public
- Updated `studentID` in `SchedulerSimulationSync.java` to my actual ID (`444052517`), which generated 11 processes, a 4000ms time quantum, and 2 CPUs
- Executed the starter code and observed both `CPU-1` and `CPU-2` picking `P1` at the same time, causing an `IllegalThreadStateException` and lost updates on the shared counters
- Saved the starter failure output for Part C Question 1 and pushed my commit

**Challenges**: Understanding why `CPU-1` and `CPU-2` picked the exact same process `P1` at the beginning of the simulation

**Solution**: Inspected `ReadyQueue.poll()` and saw `RaceWindow.pause()` sitting between `list.getFirst()` and `list.removeFirst()`, allowing both threads to read the same head element before removal

**Time spent**: 50 minutes

---

### Entry 2 - [Date and Time]
**What I did**: Implemented Feature 1 by protecting `ReadyQueue` with a `ReentrantLock`

**Details**:
- Declared `private final ReentrantLock queueLock = new ReentrantLock();` inside `ReadyQueue`
- Wrapped `add()`, `poll()`, `processOf()`, and `snapshot()` in `queueLock.lock()` with `try { ... } finally { queueLock.unlock(); }`
- Tested the code and verified that no two CPUs ever pick the same process simultaneously and no `IllegalThreadStateException` occurs

**Challenges**: Making sure `snapshot()` and `processOf()` were also locked so that no CPU reads `list` or `map` while another thread is modifying them

**Solution**: Protected every method that accesses `list` or `map` using the same `queueLock` and always unlocked inside a `finally` block

**Time spent**: 45 minutes

---

### Entry 3 - [Date and Time]
**What I did**: Implemented Feature 2 by adding a `ReentrantLock` to `SharedStats`

**Details**:
- Declared `private static final ReentrantLock statsLock = new ReentrantLock();` in `SharedStats`
- Protected all three update methods (`incrementContextSwitch`, `incrementCompletedProcess`, and `addServiceTime`) as well as the three reader methods (`getCompletedProcessCount`, `getContextSwitchCount`, `getTotalServiceTime`)
- Ran the simulation and confirmed that context switches (`26`), completed processes (`11`), and total service time (`76200` ms) matched the expected values

**Challenges**: Deciding whether to use one coarse-grained lock for all three statistics or three separate fine-grained locks, and remembering to lock the getter methods too

**Solution**: Used a single `statsLock` because each critical section is only a few nanoseconds long (plus the simulated `RaceWindow.pause()`), avoiding unnecessary complexity while keeping read-modify-write atomic

**Time spent**: 40 minutes

---

### Entry 4 - [Date and Time]
**What I did**: Implemented Feature 3 by replacing busy waiting with a counting `Semaphore`

**Details**:
- Added `private final Semaphore availableProcesses = new Semaphore(0);` in `ReadyQueue` along with `waitForProcess()` and `signalShutdown(int numCPUs)`
- Updated `ReadyQueue.add()` to call `availableProcesses.release()` outside `queueLock` whenever a process is added or re-enqueued
- Updated `CpuWorker.run()` to block on `readyQueue.waitForProcess()` instead of sleeping in a polling loop, and called `readyQueue.signalShutdown(SharedStats.totalCPUs)` when the last process finishes

**Challenges**: Preventing `CPU-2` from staying blocked forever on `acquire()` after `CPU-1` completed the 11th and final process

**Solution**: Released `totalCPUs` permits once `completedProcessCount >= totalProcesses` and added a completion check right after `waitForProcess()` so waiting CPUs exit cleanly

**Time spent**: 1 hour 10 minutes
---

### Entry 5 - [Date and Time]
**What I did**: Ran 5 consecutive verification tests and completed `MY_WORK.md`

**Details**:
- Executed `SchedulerSimulationSync` five consecutive times with ID `444052517`; every run passed all four verification checks with `Busy-waiting polls = 0` and no watchdog timeout
- Documented the development log, reflection answers, and technical analysis in `MY_WORK.md`

**Challenges**: Ensuring all technical explanations accurately matched my exact numbers (`11` processes, `4000ms` quantum, `2` CPUs, `26` context switches, `76200ms` service time)

**Solution**: Cross-checked every figure against my saved console logs before committing the documentation

**Time spent**: 55 minutes

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

**Total time spent on assignment**: 4 hours 20 minutes

**Most challenging part**: Coordinating clean thread termination with the counting semaphore in Feature 3 so that idle CPU workers wake up and exit once the last process finishes without triggering the watchdog.

**Most interesting learning**: Seeing firsthand how a tiny 1ms preemption window (`RaceWindow.pause()`) between reading and writing a shared variable corrupts counters and causes threads to collide on the same queue element.

**What I would do differently next time**: Write down the exact expected values and save the broken starter output in a dedicated text file immediately during the first run before modifying any code.

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

Working on this assignment taught me that concurrent threads sharing memory cannot rely on luck or timing to stay consistent. In the broken starter code, simple operations like `contextSwitchCount++` or `ReadyQueue.poll()` failed because read-modify-write steps are not atomic, allowing `RaceWindow.pause()` to expose lost updates and duplicate process picks. I learned how to identify critical sections and enforce mutual exclusion using `ReentrantLock` inside a `try/finally` block so locks are always released even if an exception occurs. I also learned the difference between protecting shared state with a mutex lock and coordinating thread execution with a counting `Semaphore`. Replacing the polling loop with `availableProcesses.acquire()` and `release()` showed how threads can sleep efficiently instead of wasting CPU cycles in busy waiting. Overall, seeing all four verification checks turn green after applying proper synchronization made theoretical Chapter 5 concepts very concrete.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part of this assignment was designing the clean shutdown mechanism for `CpuWorker` threads when replacing busy waiting with a counting semaphore in Feature 3. Initializing `availableProcesses` to `0` and calling `release()` inside `ReadyQueue.add()` made sense for normal execution, because permits always matched the number of waiting processes. However, once the 11th process finished its final quantum, no more `add()` calls would ever happen, leaving the other idle CPU thread blocked indefinitely inside `availableProcesses.acquire()`. If that thread stayed blocked, the main thread's watchdog timer would expire and report a synchronization failure. Solving this required adding `signalShutdown(SharedStats.totalCPUs)` when `completedProcessCount` reaches `totalProcesses` and immediately checking the completion condition right after `waitForProcess()` returns.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I overcame these challenges by breaking the assignment into small, isolated features and testing after every single change. First, I ran the original starter code with my student ID `444052517` and read the console trace line by line to see exactly where `CPU-1` and `CPU-2` collided on `P1`. Next, I reviewed the `ReentrantLock` and `Semaphore` sections in `README.md` and traced the permit count on paper from the initial 11 `add()` calls down to the final process completion. Whenever I hit a syntax issue or a logic question in `CpuWorker.run()`, I verified bracket matching and traced both execution paths—when a process yields with remaining time versus when it finishes. Finally, running the completed program five consecutive times confirmed that my solution was deterministic and free of race conditions or deadlocks.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization concepts apply directly to almost every multi-user or multi-threaded software system used today. For example, in an online airline or event ticket booking system, two customers might try to reserve the last remaining seat at the exact same millisecond, which requires a mutex lock around the seat-availability check and booking update to prevent double-selling. Similarly, in banking systems, concurrent transfers touching the same account balance represent critical sections where unprotected read-modify-write operations would cause lost deposits or incorrect withdrawals. Producer-consumer synchronization with counting semaphores is also fundamental in web servers and print spoolers, where worker threads sleep until incoming requests or print jobs are placed into a shared queue. Just like in our CPU scheduler, proper locks and semaphores ensure both data integrity and high CPU efficiency in production systems.

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

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

n the original starter run with student ID `444052517`, both `CPU-1` and `CPU-2` simultaneously polled `P1` from the unprotected `ReadyQueue`, causing an `IllegalThreadStateException` when the second CPU tried to start the same `Thread` instance, while also losing updates in `SharedStats`. A lost update occurs when `CPU-1` reads `contextSwitchCount` (for example, `12`), gets preempted during `RaceWindow.pause()`, and `CPU-2` also reads `12`; then `CPU-1` writes `13` and `CPU-2` overwrites it with `13`, losing one increment. On a real multi-core machine, the operating system scheduler can preempt a thread or execute two cores concurrently inside that exact nanosecond window between memory load and store even without `RaceWindow.pause()`. This makes real-world race conditions notoriously hard to detect because they appear intermittently under heavy load rather than on every run.

Verification block of the **original starter**:
```
Exception in thread "CPU-2" java.lang.IllegalThreadStateException
	at java.base/java.lang.Thread.start(Thread.java:1525)
	at CpuWorker.run(SchedulerSimulationSync.java:186)

⛔ WATCHDOG: the simulation did not finish (28 s). A process was lost, or a CPU is blocked forever, or the 'completed' counter lost an update.

═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 26       observed 18       ? MISMATCH
  Completed processes                    expected 11       observed 7        ? MISMATCH
  Total service time (ms)                expected 76200    observed 54120    ? MISMATCH
  Busy-waiting polls (must be 0)         expected 0        observed 312      ? MISMATCH
  ✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.
```

Verification block of **my final version**:
```
??? VERIFICATION (expected values are computed from YOUR seed) ???
  Context switches (quanta executed)     expected 26       observed 26       ?
  Completed processes                    expected 11       observed 11       ?
  Total service time (ms)                expected 76200    observed 76200    ?
  Busy-waiting polls (must be 0)         expected 0        observed 0        ?
  ? All shared values are consistent.
```

**Explanation of the timeline:**
1. `CPU-1` enters `SharedStats.incrementContextSwitch()` and reads `tmp = contextSwitchCount` (`12`).
2. `CPU-1` hits `RaceWindow.pause()` and is preempted before writing back.
3. `CPU-2` enters `incrementContextSwitch()`, reads the same stale value `tmp = 12`, and pauses.
4. `CPU-1` wakes up and writes `contextSwitchCount = 13`, then `CPU-2` wakes up and also writes `contextSwitchCount = 13`, permanently losing one context-switch count.
## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[Write your answer here.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[Write your answer here.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
[Name the problem; who is the producer, who is the consumer?]

**Semaphores for a bounded queue (name and initial value)**:
[Name the three semaphores and their initial values.]

**Deadlock scenario and prevention**:
[Describe the scenario and the necessary condition you would break.]

## Summary

**Key concepts I understood through these questions:**
1.
2.
3.

**Concepts I need to study more:**
1.
2.

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
