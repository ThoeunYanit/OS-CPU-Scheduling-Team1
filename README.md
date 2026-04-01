# CPU Scheduling Algorithm Simulator

> **OS-CPU-Scheduling-Team1** | Year 2 Term 2 — Operating Systems Project  
> Language: **JavaScript** | No install required — open `index.html` in any browser

---

## 🚀 How to Run

```
1. Download index.html
2. Double-click it (or drag it into Chrome / Firefox / Edge)
3. That's it.
```

No Node.js, no npm, no Python, no server needed.

---

## 📂 Files

```
OS-CPU-Scheduling-Team1/
├── index.html   ← The entire application (HTML + CSS + JS in one file)
└── README.md    ← This file
```

---

## 🧠 Algorithms

| # | Name | Type | Key Idea |
|---|------|------|----------|
| 1 | FCFS | Non-preemptive | Run in arrival order |
| 2 | SJF  | Non-preemptive | Pick shortest burst next |
| 3 | SRT  | Preemptive | Always run shortest *remaining* burst |
| 4 | Round Robin | Preemptive | Time-slice rotation (configurable quantum) |
| 5 | MLFQ | Preemptive | 3-level queue with demotion + aging |

### MLFQ Structure
```
Q0 → Round Robin, quantum = Q     (highest priority)
Q1 → Round Robin, quantum = 2×Q
Q2 → FCFS                         (lowest priority)

Demotion : use full quantum → drop to next queue
Promotion: wait ≥ 10 ticks → move up one queue (anti-starvation)
```

---

## 📊 Sample Output (Default Scenario)

Input: P1(0,5), P2(1,3), P3(2,8), P4(3,6) | Quantum = 2

```
Algorithm    Avg WT    Avg TAT    Avg RT
-----------------------------------------
FCFS          5.75      11.25      5.75
SJF           5.25      10.75      5.25
SRT           5.00      10.50      4.25   ← Best WT & TAT
RR (q=2)      9.75      15.25      2.00
MLFQ          9.25      14.75      1.50   ← Best RT
```

---

## 🖥 How to Use the App

1. **Edit process rows** — change PID, Arrival Time, Burst Time
2. **Add/Remove processes** with the buttons
3. **Pick an algorithm** — or leave on "Run All" to compare all five
4. **Set the quantum** for Round Robin and MLFQ
5. **Click ▶ Run Simulation**
6. See the **Gantt chart** and **metrics table** for each algorithm
7. A **Comparative Summary** table appears at the bottom when running all

---

## 📐 Metrics

| Metric | Formula |
|--------|---------|
| Turnaround Time (TAT) | Finish Time − Arrival Time |
| Waiting Time (WT) | TAT − Burst Time |
| Response Time (RT) | First CPU access − Arrival Time |

---



