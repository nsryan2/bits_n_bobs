# `perf` on Linux

`perf` is a powerful performance analysis tool for Linux systems. It provides a wide range of capabilities for profiling and tracing system performance.


## Installing `perf`
To install `perf`:
```sh
sudo apt-get install linux-tools-common linux-tools-generic linux-tools-$(uname -r)
```


## Runtime Stats
Running a high-level overview:
```sh
perf stat <command>
```

Here is an example of what the output might look like:

```sh
 Performance counter stats for '<command>':

       12345.678901      task-clock (msec)         #    1.234 CPUs utilized
               123      context-switches          #    0.010 K/sec
                 0      cpu-migrations            #    0.000 K/sec
               456      page-faults               #    0.037 K/sec
   123456789012      cycles                      #    1.000 GHz
   123456789012      instructions                #    1.000  insn per cycle
   123456789012      branches                    #    1.000 M/sec
   123456789012      branch-misses               #    1.000 % of all branches

      10.000123456 seconds time elapsed
```

### Explanation of Metrics:
- task-clock (msec): Total time the task was running on the CPU.
- context-switches: Number of context switches.
- cpu-migrations: Number of times the process was migrated to a different CPU.
- page-faults: Number of page faults.
- cycles: Total CPU cycles.
- instructions: Total instructions executed.
- branches: Total branch instructions.
- branch-misses: Number of branch misses.
- seconds time elapsed: Total elapsed time for the command execution.


## Recording Performance Data
To record detailed performance data for a specific command:
```sh
perf record -F 99 -a -g -- sleep 10
```
- `-F 99`: Sets the sampling frequency to 99 Hz.
- `-a`: Records system-wide.
- `-g`: Captures call graphs.
- `-- sleep 10`: Runs the `sleep` command for 10 seconds.


## Viewing Performance Data
To view the recorded performance data:
```sh
perf report
```
This command opens an interactive report of the recorded data, showing hotspots and call graphs.


## Analyzing CPU Usage
To analyze CPU usage:
```sh
perf stat -a sleep 5
```
- `-a`: Collects statistics system-wide.
- `sleep 5`: Runs the `sleep` command for 5 seconds.


## Profiling a Specific Process
To profile a specific process by its PID:
```sh
perf record -p <pid> -g -- sleep 10
```
- `-p <pid>`: Profiles the process with the given PID.
- `-g`: Captures call graphs.
- `-- sleep 10`: Runs the `sleep` command for 10 seconds.


## Tracing System Calls
To trace system calls:
```sh
perf trace
```
This command provides a trace of system calls made by all processes.


## Monitoring Hardware Events
To monitor specific hardware events:
```sh
perf stat -e cycles,instructions,cache-references,cache-misses -a sleep 5
```
- `-e cycles,instructions,cache-references,cache-misses`: Specifies the hardware events to monitor.
- `-a`: Collects statistics system-wide.
- `sleep 5`: Runs the `sleep` command for 5 seconds.


## Using `perf top`
To view real-time performance data:
```sh
perf top
```
This command provides a real-time view of system performance, similar to the `top` command but with more detailed performance metrics.
