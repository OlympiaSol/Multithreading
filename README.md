Sure, here is the revised README file in the past tense:

---

# Multithreaded Storage Engine Implementation

## Overview

This project was part of the MYY601 Operating Systems course at the University of Ioannina. The main objective was to implement multithreading functionalities for the `add` and `get` commands in a provided storage engine coded in C. The storage engine is based on the log-structured merge (LSM) tree and aims to handle simultaneous operations from multiple threads efficiently.

## Project Description

### Storage Engine

The provided storage engine, Kiwi, utilizes the LSM-tree data structure. LSM-trees are widely used in modern cloud infrastructures for scalable and reliable data storage and retrieval. The API offered `add` and `get` operations for key-value pairs. 

- **`add` Operation**: Added a key-value pair to the storage.
- **`get` Operation**: Retrieved the value associated with a given key.

The engine maintained data in a sorted structure in memory (memtable) and periodically merged this with disk-stored files (sstables) to optimize performance.

### Multithreading Implementation

The enhancement to the provided storage engine supported concurrent execution of `add` and `get` operations using multiple threads. This implementation ensured correct operation and maintained performance statistics for each function.

## Getting Started

### Prerequisites

- **C Programming Language**: The implementation was done in C.
- **Pthreads Library**: Used the Pthreads library for thread management and synchronization.
- **Virtual Machine**: Downloaded and set up the provided virtual machine running Debian Linux 64-bit.

### Running the Benchmark

1. Inserted a set of items into the storage engine:
   ```sh
   ./kiwi-bench write 10000
   ```
2. Read the items back:
   ```sh
   ./kiwi-bench read 10000
   ```

### Implementation Steps

1. **Explored Existing Threads**: Investigated the current implementation of threads in the application and storage engine.
2. **Basic Synchronization**: Implemented mutual exclusion to ensure that only one operation (either `add` or `get`) accessed the storage engine at a time.
3. **Advanced Synchronization**: Used reader-writer locks to allow multiple `get` operations to execute concurrently, while ensuring that `add` operations were executed exclusively.
4. **Performance Measurement**: Ensured accurate performance measurement by synchronizing the update of performance metrics across different threads.


## Additional Resources

- [GDB Cheat Sheet & Reference](https://sourceware.org/gdb/download/onlinedocs/gdb.html)
- [Kiwi Code Documentation](https://www.cse.uoi.gr/~stergios/teaching/myy601/lab/kiwi-dox/html/)

---

## Useful Links

- Documentation: https://docs.askthecode.ai
- GitHub: https://github.com/askthecode/documentation
- Twitter: https://twitter.com/askthecode_ai


For more details, feel free to take a look at my report PDF file. Here is a brief summary of what the PDF contains:

- **Introduction**: Overview of the project objectives and requirements.
- **Setup Instructions**: Steps to set up the virtual machine and necessary software.
- **Implementation Details**: Detailed explanation of the multithreading implementation, including synchronization techniques and code modifications.
- **Performance Evaluation**: Results of performance tests under different scenarios and analysis of the outcomes.
- **Conclusion**: Summary of the project's achievements and potential areas for improvement.

You can find the full report in the attached `Report.pdf` file.
