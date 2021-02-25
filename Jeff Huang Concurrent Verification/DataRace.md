## Data Races:

The Thread Analyzer detects data-races that occur during the execution of a multi-threaded process. A data race occurs when:

- two or more threads in a single process access the same memory location concurrently;

- at least one of the accesses is for writing;

- the threads are not using any exclusive locks to control their accesses to that memory;

When these three conditions hold, the order of accesses is non-deterministic, and the computation may give different results from run to run depending on that order. Some data-races may be benign.

========================

### Jeff Huang-PLDI 2018: D4: Fast Concurrency Debugging with Parallel Differential Analysis
----------
`Main focus`:

They propose D4, a fast concurrent analysis framework that detects concurrency bugs
(data races and deadlocks of java program). It can provides immediate feedback in programing phase(add, modify, remove statements). D4 contains two new static analysis techniques:

- incremental pointer analysis.

- static happens-before analysis.

Both two analysis can be parallelized. Evaluation on real-world applications shows that
D4 can report concurrency bugs within 0.1s on average and several orders of magnitude faster than other state-of-the-art incremental techniques. Their tool D4 is available(https://github.com/parasol-aser/D4), both source code and plugin in Eclipse.

----------
