Parallel and Distributed Computing – Chapter 5 

Prepared by: Maham
Course: Parallel and Distributed Computing (PDC) Chapter 5

Objective
The objective of this chapter is to understand asynchronous programming, task scheduling, and parallel execution in Python using asyncio and concurrent.futures. Each example demonstrates how multiple tasks or threads can execute concurrently, manage shared resources, and improve performance.

Tools & Technologies
Language: Python 3.11+
Modules Used: asyncio, concurrent.futures, random, time
IDE: Visual Studio Code

Folder Structure:
PDC-Chap5/
│ math_task.py
│ asyncio_futures_test.py
│ asyncio_coroutine_test.py
│ asyncio_eventloop_test.py
│ asyncio_task_manipulation_test.py
│ concurrent_futures_test.py
│ README.md

File Descriptions

math_task.py
Objective: Implements do_something(count, out_list) that generates random numbers and computes the sum of their cubes.
Theory: Used in all examples to simulate CPU-bound work.
Code Explanation: Generates count random numbers, computes sum of cubes, and appends to out_list.
Expected Output: Displays cumulative sum of cubes.

asyncio_futures_test.py
Objective: Demonstrates asynchronous execution using asyncio Futures and callbacks.
Theory: Futures represent values computed asynchronously. Callbacks execute when futures complete.
Code Explanation: Wraps do_something() in an async function, uses Future objects to store results, and registers a callback to print results when computation finishes.
Expected Output: Prints sum of cubes for each task once done.

asyncio_coroutine_test.py
Objective: Demonstrates a Finite State Machine (FSM) pattern with asynchronous tasks.
Theory: Each function represents a state; transitions occur with await. The end state produces the final result.
Code Explanation: start_state() begins execution, transitions randomly between compute_state, alternate_state, and verify_state, end_state() prints final sum.
Expected Output: Step-by-step transition between states, ending with final sum of cubes.

asyncio_eventloop_test.py
Objective: Demonstrates event-loop scheduling using loop.call_soon() and loop.call_later().
Theory: Functions schedule each other to run later without coroutines.
Code Explanation: task_A, task_B, and task_C call each other cyclically; loop.stop() stops execution after a set duration.
Expected Output: Tasks print messages in a loop until time expires.

asyncio_task_manipulation_test.py
Objective: Executes multiple async tasks in parallel using asyncio.create_task().
Theory: Multiple tasks can run concurrently in the event loop.
Code Explanation: Wraps do_something() in async functions, creates multiple tasks, and runs them concurrently using await asyncio.wait().
Expected Output: Prints sum of cubes for each task; order may vary due to parallel execution.

concurrent_futures_test.py
Objective: Demonstrates parallel execution using concurrent.futures with ThreadPool and ProcessPool.
Theory: ThreadPoolExecutor is ideal for I/O-bound tasks, ProcessPoolExecutor is ideal for CPU-bound tasks.
Code Explanation: Executes do_something() sequentially, with threads, and with processes; compares execution times.
Expected Output: Displays sum of cubes for each task and execution times for sequential, thread pool, and process pool modes.

Overall Conclusion
This collection of programs demonstrates asynchronous programming, task scheduling, and parallel execution in Python. asyncio allows cooperative multitasking and FSM-style asynchronous flows. asyncio.Task runs multiple async computations concurrently. concurrent.futures enables parallel execution using threads or processes. These techniques prevent blocking, maximize CPU utilization, and efficiently manage concurrent tasks.

How to Run
In your terminal, run the Python script:

python filename.py

Example:

python asyncio_futures_test.py
