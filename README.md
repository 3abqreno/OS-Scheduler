# CPU Scheduler Simulation - Readme

This project simulates a CPU scheduler on Linux using C. It evaluates different scheduling algorithms, practices IPC, and implements efficient algorithms and data structures.

## Implemented Algorithms

### Scheduling Algorithms (In `scheduler.c`)

The scheduler component implements the following three scheduling algorithms:

1. **Non-preemptive Highest Priority First (HPF):**
   - Prioritizes processes based on their priority values (0 to 10).
   - Highest priority processes are scheduled first.
   - Non-preemptive, meaning a process continues until completion.

2. **Shortest Remaining Time Next (SRTN):**
   - Chooses the process with the shortest remaining time for execution.
   - Preemptive, allowing the scheduler to switch between processes based on their remaining time.

3. **Round Robin (RR):**
   - Allocates a fixed time slice to each process in a circular order.
   - Preemptive, ensuring fair execution among processes.
## Memory Allocation Algorithms

1. **First Fit:**
  - Scans available memory blocks.
  - Allocates the first block large enough for the process.
  - Tracks allocated memory.
  - Logs allocation details in `memory.log` file.

2. **Buddy Memory Allocation:**
  - Divides total memory into power-of-two-sized blocks.
  - Allocates the smallest available block for the process.
  - Splits blocks into buddies if needed.
  - Merges neighboring free blocks upon process exit.
  - Logs allocation and deallocation details in `memory.log` file.

These algorithms collectively ensure effective utilization of the total memory space, dynamically allocating and deallocating memory for arriving and departing processes.


## Project Components

### 1. Process Generator (`process_generator.c`):
- Reads input files.
- Initiates scheduler and clock processes.
- Sends process information to the scheduler.

### 2. Clock (`clk.c`):
- Emulates an integer time clock for simulation and IPC.

### 3. Scheduler (`scheduler.c`):
- Implements HPF, SRTN, and RR algorithms.
- Manages process states and PCBs.
- Generates `Scheduler.log` and `Scheduler.perf` files.

### 4. Process (`process.c`):
- Acts as a CPU-bound process.
- Notifies scheduler on termination.

### 5. Input/Output:
- **Input File (`processes.txt`):** Defines processes.
- **Output Files:**
   - `scheduler.log` (example provided)
   - `scheduler.perf` (example provided)
   - `memory.log` (example provided)

## How to Run

To compile and run your project, follow the commands below:

1. **Compilation:**
    ```bash
    make
    ```

    This command will compile your project using the specified build settings.

2. **Execution:**
    ```bash
    make run
    ```

    Use this command to run your compiled project. Ensure that the compilation step is successful before executing this command.

3. Review `scheduler.log` and `scheduler.perf` for logs and performance metrics.
