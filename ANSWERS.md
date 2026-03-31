# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[process: independent program with its own memory space, resources, and execution environment.
thread: a lightweight unit of execution that runs inside a process and shares the same memory and resources with other threads in that process.
we used the thread because it requires less overhead to create and switch between compared to processes, which makes them faster and more efficient for like this assignment, i used them instead because the goal was to simulate cpu scheduling behavior without the heavy coost of creating multiple processes. using threads allowed the simulation to run smoothly while still demonstrating concurrency and scheduiling concepts. ]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

[n Round-Robin scheduling, if a process does not finish within its assigned *time quantum, it is **interrupted* and placed back into the *ready queue*. This ensures fairness by giving every process a chance to run without letting any single process monopolize the CPU. The process will run again only after all other ready processes have had their turn.]

Example from my output:
```
[
? P5 yields CPU for context switch
? P5 (Priority: 1) added to ready queue ? Burst time: 9806ms
?? Ready Queue: P6, P7, P8, P9, P10, P12, P14, P5
]
```

**Explanation of example:**
[Here, process P5’s time quantum expired before it finished its burst time. The scheduler preempted it and placed it at the end of the ready queue, allowing other processes to run next. This demonstrates the Round‑Robin behavior of fair CPU sharing]

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[Here is how process P1 moves through the thread states in the simulation:]

1. **New**: [When is P1 in New state?:when it is created but before the thread starts executing.]

2. **Runnable**: [When does P1 become Runnable?:when it is created but before the thread starts executing.]

3. **Running**: [When is P1 Running?:When the scheduler selects P1 and assigns it the CPU for its time quantum, it enters the Running state.]

4. **Waiting**: [When/why would P1 be Waiting?: if it is preempted and placed back into the ready queue, waiting for its next turn.]

5. **Terminated**: [When is P1 Terminated?: once P1 finishes all its burst time and no longer needs CPU time, it enters the Terminated state and is removed from the scheduling cycle.]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Operating System Task Scheduling]

**Description**: 
[Modern operating systems use Round-Robin scheduling for time-sharing among user applications, especially when many programs are running at once.]

**Why Round-Robin works well here**: 
[It ensures fairness by giving each task a fixed time slice, preventing any single program from freezing the system. It also keeps the system responsive, which is essential for multitasking environments.]

### Example 2: [Multiplayer Online Games]

**Description**: 
[Game servers often handle many player actions concurrently—movement, attacks, chat messages, etc.—using threads.]

**Why Round-Robin works well here**: 
[It ensures that every player’s actions are processed regularly and fairly. No single player or background task can dominate the server’s CPU time, which keeps gameplay smooth and predictable.]

---

## Summary

**Key concepts I understood through these questions:**
1. The difference between threads and processes
2. How Round-Robin scheduling ensures fairness
3. How thread states change during execution

**Concepts I need to study more:**
1. Synchronization and avoiding race conditions 
2. How real operating systems implement advanced scheduling algorithms  

