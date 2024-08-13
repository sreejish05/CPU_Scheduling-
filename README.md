# CPU-Scheduling-Algorithms

An implementation of various CPU scheduling algorithms in C++. The algorithms included are First Come First Serve (FCFS), Round Robin (RR), Shortest Process Next (SPN), Shortest Remaining Time (SRT), Highest Response Ratio Next (HRRN), Feedback (FB), and Aging.

## Table of Contents
- [CPU-Scheduling-Algorithms](#cpu-scheduling-algorithms)
  - [Algorithms](#algorithms)
    - [First Come First Serve (FCFS)](#first-come-first-serve-fcfs)
    - [Round Robin with varying time quantum (RR)](#round-robin-with-varying-time-quantum-rr)
    - [Shortest Process Next (SPN)](#shortest-process-next-spn)
    - [Shortest Remaining Time (SRT)](#shortest-remaining-time-srt)
    - [Highest Response Ratio Next (HRRN)](#highest-response-ratio-next-hrrn)
    - [Feedback (FB)](#feedback-fb)
    - [Feedback with varying time quantum (FBV)](#feedback-with-varying-time-quantum-fbv)
    - [Aging](#aging)
  - [Installation](#installation)
  - [Input Format](#input-format)
  - [Contributors](#contributors)

## Algorithms

### First Come First Serve (FCFS)
- First Come First Served (FCFS) is a scheduling algorithm in which the process that arrives first is executed first. It is a simple and easy-to-understand algorithm, but it can lead to poor performance if there are processes with long burst times. This algorithm does not have any mechanism for prioritizing processes, so it is considered a non-preemptive algorithm. In FCFS scheduling, the process that arrives first is executed first, regardless of its burst time or priority. This can lead to poor performance, as longer-running processes will block shorter ones from being executed. It is commonly used in batch systems where the order of the processes is important.

### Round Robin with varying time quantum (RR)
- Round Robin (RR) with variable quantum is a scheduling algorithm that uses a time-sharing approach to divide CPU time among processes. In this version of RR, the quantum (time slice) is not fixed and can be adjusted depending on the system’s needs or process characteristics. This helps to provide a more flexible and fair allocation of CPU time, reducing the chance of process starvation.

### Shortest Process Next (SPN)
- Shortest Process Next (SPN) is a scheduling algorithm that selects the process with the shortest estimated run time to execute next. It is a non-preemptive version of the Shortest Remaining Time algorithm. SPN minimizes the average waiting time but can cause starvation of longer processes.

### Shortest Remaining Time (SRT)
- Shortest Remaining Time (SRT) is a preemptive scheduling algorithm that selects the process with the shortest remaining execution time. If a new process arrives with a shorter remaining time than the current running process, the current process is preempted. This approach minimizes the average waiting time but can lead to process starvation for longer jobs.

### Highest Response Ratio Next (HRRN)
- Highest Response Ratio Next (HRRN) is a non-preemptive scheduling algorithm that selects the process with the highest response ratio to execute next. The response ratio is calculated as the sum of the waiting time and service time divided by the service time. This algorithm aims to balance between short and long processes by increasing the priority of processes that have waited longer.

### Feedback (FB)
- The Feedback (FB) scheduling algorithm is a multi-level queue algorithm where processes are moved between queues based on their execution history. Processes start in the highest-priority queue and are gradually moved to lower-priority queues if they use more CPU time. This approach ensures that short processes are executed quickly while longer processes are gradually deprioritized.

### Feedback with varying time quantum (FBV)
- Feedback with varying time quantum (FBV) is a variation of the Feedback scheduling algorithm where each queue has a different time quantum. This approach allows for a more fine-tuned CPU time allocation, where shorter processes are given smaller time quanta and longer processes are given larger quanta as they move down the priority queues.

### Aging
- The Aging scheduling algorithm is designed to prevent starvation by gradually increasing the priority of processes that wait in the queue for a long time. As a process waits, its priority increases, ensuring that it will eventually be executed even if it started with a low priority.

## Installation

1. Clone the repository

2. Install g++ compiler and make
    ```bash
    sudo apt-get install g++ make
    ```
3. Compile the code using `make` command

4. Run the executable file

## Input Format

- Line 1: "trace" or "stats"
- Line 2: A comma-separated list telling which CPU scheduling policies to be analyzed/visualized along with their parameters, if applicable. Each algorithm is represented by a number as listed in the introduction section and as shown in the attached test cases. Round Robin and Aging have a parameter specifying the quantum `q` to be used. Therefore, a policy entered as `2-4` means Round Robin with `q=4`. Also, policy `8-1` means Aging with `q=1`.
  1. FCFS (First Come First Serve)
  2. RR (Round Robin)
  3. SPN (Shortest Process Next)
  4. SRT (Shortest Remaining Time)
  5. HRRN (Highest Response Ratio Next)
  6. FB-1, (Feedback where all queues have q=1)
  7. FB-2i, (Feedback where q= 2i)
  8. Aging
- Line 3: An integer specifying the last instant to be used in your simulation and to be shown on the timeline.
- Line 4: An integer specifying the number of processes to be simulated.
- Line 5: Start of description of processes. Each process is to be described on a separate line. For algorithms 1 through 7, each process is described using a comma-separated list specifying:
    1. String specifying a process name
    2. Arrival Time
    3. Service Time
- **Note:** For Aging algorithm (algorithm 8), each process is described using a comma-separated list specifying:
    1. String specifying a process name
    2. Arrival Time
    3. Priority
- Processes are assumed to be sorted based on the arrival time. If two processes have the same arrival time, then the one with the lower priority is assumed to arrive first.



