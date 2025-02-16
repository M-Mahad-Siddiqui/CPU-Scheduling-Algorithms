# CPU Scheduling Simulator

## Introduction

This project is a **CPU Scheduling Simulator** that helps visualize and understand different CPU scheduling algorithms. CPU scheduling plays a crucial role in operating systems as it determines how processes are allocated CPU time, directly affecting system performance and efficiency.

The simulator allows users to select various scheduling algorithms, input process details, and observe scheduling orders, waiting times, turnaround times, and overall efficiency.

## How It Works

- The user selects a **scheduling algorithm** from the available options.
- The user **uploads a file** containing process details (arrival time, burst time, priority, etc.).
- The program **parses the input** and applies the selected scheduling algorithm.
- The results are **displayed**, showing process execution order, Gantt charts, and performance metrics.

## CPU Scheduling Algorithms Implemented

### 1. **First Come First Serve (FCFS)**

- **Description**: The simplest scheduling algorithm, where the process that arrives first is executed first.
- **Working**:
  - Non-preemptive.
  - Processes are executed in the order they arrive in the ready queue.
  - The CPU executes each process until completion.
- **Use Case**: Suitable for batch processing where tasks can be executed in order without time constraints.
- **Advantages**:
  - Simple and easy to implement.
  - No starvation (every process gets executed in arrival order).
- **Disadvantages**:
  - **Convoy Effect**: Long processes can block shorter ones, resulting in higher waiting times.
  - Longer waiting times for later-arriving processes.

---

### 2. **Shortest Job First (SJF)**

- **Description**: The process with the shortest burst time is executed first, minimizing average waiting time.
- **Working**:
  - **Non-preemptive**: Once a process starts, it runs until completion.
  - **Preemptive (SRTF - Shortest Remaining Time First)**: If a new process with a shorter burst time arrives, it preempts the current process.
- **Use Case**: Ideal in scenarios where execution time is known in advance, like job scheduling in batch systems.
- **Advantages**:
  - **Optimal** for minimizing average waiting time.
  - Efficient in systems where burst times are predictable.
- **Disadvantages**:
  - **Starvation**: Long processes may never be executed if shorter jobs keep arriving.
  - Difficulty in accurately predicting burst times.

---

### 3. **Priority Scheduling**

- **Description**: Processes are executed based on priority. The highest priority process runs first.
- **Working**:
  - **Non-preemptive**: The CPU executes a process to completion once it starts.
  - **Preemptive**: If a higher-priority process arrives, it preempts the current process.
- **Use Case**: Suitable for real-time systems where urgent tasks need immediate execution (e.g., embedded systems, network applications).
- **Advantages**:
  - Critical tasks are executed first.
  - Ideal for systems with tasks that vary in importance.
- **Disadvantages**:
  - **Starvation**: Low-priority tasks may never get executed if higher-priority tasks keep arriving.
  - Priority assignment can be complex and error-prone.

---

### 4. **Round Robin (RR) [Highly Detailed]**

- **Description**: Each process is given a fixed time slice or **quantum** before switching to the next process in the queue, ensuring fairness across all processes.

- **Working**:

  - The CPU executes each process for a predefined time quantum.
  - If a process does not complete within that quantum, it is sent to the end of the queue.
  - The next process in the queue is executed until it either completes or reaches its time quantum.

- **Example**: Suppose we have 3 processes with the following burst times:

  - **P1**: 10ms
  - **P2**: 5ms
  - **P3**: 7ms\
    And the **time quantum** is 3ms. The execution order will be:

  ```
  P1 (3ms) → P2 (3ms) → P3 (3ms) → P1 (3ms) → P3 (3ms) → P1 (1ms) → P3 (1ms)
  ```

- **Use Case**:

  - Commonly used in **time-sharing systems**, where multiple users share the CPU.
  - Suitable for interactive applications, ensuring that all users/processes get timely CPU access.

- **Advantages**:

  - **Fairness**: Every process gets an equal chance to use the CPU.
  - No starvation: Every process eventually gets executed.
  - Suitable for multi-user and interactive systems.

- **Disadvantages**:

  - **Context Switching**: Frequent switching between processes can introduce overhead.
  - Performance heavily depends on the **time quantum**:
    - If too small, excessive context switching reduces efficiency.
    - If too large, it behaves like **FCFS**, leading to inefficiency.

---

## Purpose of the Project

This project aims to:

- Provide an **interactive learning tool** for understanding CPU scheduling algorithms.
- Help students and professionals **visualize the working** of different scheduling techniques.
- Compare **different scheduling algorithms** based on efficiency and performance.
- Demonstrate how the **time quantum** in Round Robin scheduling can significantly impact performance.

## Where It Is Used

- **Operating Systems**: Scheduling user applications and system tasks.
- **Cloud Computing**: Efficient management of virtual machines and resources.
- **Embedded Systems**: Ensuring timely execution of real-time tasks.
- **Multi-User Systems**: Distributing CPU time among users to ensure fairness.

## Advantages of CPU Scheduling

- **Maximizes CPU utilization**: Prevents CPU idle time by assigning processes efficiently.
- **Improves throughput**: Increases the number of processes completed in a given time.
- **Reduces waiting time**: Optimizes process execution order for better efficiency.
- **Ensures fairness**: Ensures each process gets an opportunity to run, avoiding indefinite delays.

## Disadvantages of CPU Scheduling

- **Complexity**: Implementing and selecting the best scheduling algorithm requires careful consideration.
- **Overhead**: Context switching between processes can add computational delays.
- **Starvation**: Some scheduling algorithms, like Priority Scheduling, may lead to certain processes being indefinitely delayed.

## Conclusion

This CPU Scheduling Simulator is a powerful tool for understanding and comparing different scheduling techniques. It provides detailed execution analysis and helps in learning how modern operating systems manage process scheduling.



