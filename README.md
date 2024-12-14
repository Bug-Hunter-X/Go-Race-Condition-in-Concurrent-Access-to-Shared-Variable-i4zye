# Go Race Condition Example

This repository demonstrates a common race condition in Go programs that involves concurrent access to a shared variable without proper synchronization.  The example showcases the unpredictable results that can arise from this issue and provides a solution using mutexes.

## Bug Description

The `bug.go` file contains a Go program that uses goroutines to increment a shared counter variable (`count`). Without proper synchronization, multiple goroutines might try to modify `count` simultaneously, leading to data races and incorrect results. The output of the program will vary on each run, highlighting the non-deterministic nature of the bug.

## Solution

The `bugSolution.go` file presents a corrected version of the program. It uses a mutex (`sync.Mutex`) to protect the shared counter, ensuring that only one goroutine can access and modify `count` at any given time. This approach prevents data races and yields a consistent, correct result.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's root directory.
3. Run the buggy code: `go run bug.go` Observe the inconsistent output.
4. Run the fixed code: `go run bugSolution.go` Observe the consistent output.