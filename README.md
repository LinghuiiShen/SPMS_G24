# SmartPark — Smart Parking Management System

**COMP2432 — Operating Systems Course Project (2025)**

A parking management system for The Hong Kong Polytechnic University. SmartPark processes individual and batch bookings, allocates resources using FCFS, priority-based, and optimized scheduling, and generates booking and resource-utilization reports.

**Technologies:** C (C99), POSIX processes (`fork`), pipes, shared memory, pthread mutexes, and GCC.

## Repository Structure

- `src/`: input handling, scheduling, resource management, output, and utility modules.
- `examples/`: seven batch input files.
- `docs/`: [project report](docs/Project_Report_G24.pdf), [original instructions](docs/original-readme.txt), and archived sample output.

## Build and Run

On Linux (the original project targets PolyU's Apollo environment), run from the repository root:

```bash
mkdir -p build
gcc -std=c99 src/input_module.c src/output_module.c src/scheduler.c src/utils.c src/resource.c src/main.c -o build/spms -lrt -lpthread -lm
./build/spms
```

At the application prompt, load a sample batch:

```text
addBatch -examples/batch004.dat
```

Wait for the next input prompt, then display results:

```text
printBookings -all
```

Use `-fcfs`, `-prio`, or `-opti` instead of `-all` to select one scheduling algorithm. See the original instructions for booking syntax and scheduling assumptions.

The program writes `input_commands.txt` and `analysis_report.txt` in the working directory, clearing them at startup. Archived output in `docs/` is kept separately.
