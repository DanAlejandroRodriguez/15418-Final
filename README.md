# Parallel Monte Carlo Tree Search (MCTS) in Reinforcement Learning with Trainium

**Team:** Daniel Rodriguez (Solo)

**Project URL:** [https://danalejandrorodriguez.github.io/15418-Final/](https://danalejandrorodriguez.github.io/15418-Final/)

---

## Summary

This project will implement a parallel Monte Carlo Tree Search (MCTS) algorithm integrated within a reinforcement learning framework, leveraging Amazon Trainium to accelerate compute-intensive parts of the search. The approach employs distributed-memory programming via MPI alongside Trainium’s Neuron SDK to boost performance and scalability on large decision trees.

---

## Background

Monte Carlo Tree Search (MCTS) is a powerful algorithm used in reinforcement learning and game AI for exploring large search spaces by simulating many random playouts. In many applications, such as complex board games or decision-making systems, the computational cost of exploring the vast search tree can be prohibitive on a single core. In this project, I will build a serial MCTS algorithm from scratch as a baseline and then develop a parallel version that distributes the simulation workload across MPI processes. Amazon Trainium will be employed to accelerate the random playouts and evaluation functions, which are the most compute-intensive parts of the algorithm. This integration will allow us to tackle larger and more complex decision trees than is feasible with conventional hardware alone.

---

## The Challenge

Parallelizing MCTS is challenging due to:
- **Irregular Workloads:** The search tree can grow in unpredictable ways, leading to load imbalances.
- **Synchronization Overhead:** Global updates (such as propagating rewards and updating tree nodes) require careful synchronization to avoid stalling the parallel processes.
- **Integration with Trainium:** Offloading compute-intensive playouts to Trainium requires efficient data transfers and overlap of computation and communication.
These challenges necessitate a design that minimizes global communication while fully exploiting Trainium’s acceleration capabilities.

---

## Resources

- **Hardware:** Amazon Trainium instances (using the Neuron SDK) and PSC/GHC cluster nodes.
- **Software:** C/C++ for the core implementation, MPI for distributed communication, and standard profiling tools (perf and TAU) for performance evaluation.
- **References:** Research papers on parallel MCTS, reinforcement learning, and Trainium acceleration techniques, alongside relevant 15‑418/15‑618 course materials.

---

## Goals and Deliverables

The primary goal is to develop both a serial and a parallel version of the MCTS algorithm integrated within a reinforcement learning framework. The serial version will be implemented from scratch as a baseline. The parallel version will use MPI to distribute simulations and leverage Amazon Trainium to accelerate playout evaluations. Deliverables include the complete source code, detailed performance analysis with scalability graphs, and a final report and poster summarizing methodology and experimental results.

---

## Platform Choice

Amazon Trainium is chosen because its architecture is optimized for tensor and matrix operations commonly found in deep learning and reinforcement learning workloads. By integrating Trainium with an MPI-based distributed system, this project can efficiently accelerate the computationally heavy components of MCTS while scaling the overall search process.

---

## Schedule

| Date Range        | Task Description                                                                                                                                             |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mar 26 - Apr 1    | Finalize project design; implement the serial MCTS algorithm (from scratch) as the baseline.                                                                 |
| Apr 2 - Apr 8     | Set up the MPI environment and partition the search space across processes; integrate initial Trainium-accelerated kernels using the Neuron SDK.            |
| Apr 9 - Apr 15    | Refine and optimize the Trainium-accelerated playout evaluations; begin collecting performance data using perf and TAU.                                       |
| Apr 16 - Apr 22   | Optimize global tree updates and reduce communication overhead; profile synchronization and load balancing across MPI processes.                             |
| Apr 23 - Apr 28   | Conduct comprehensive benchmarking; generate detailed performance graphs; prepare the final report and poster for the session on April 29th.                 |

---

This project is designed to address complex challenges in parallel decision-making and reinforcement learning, leveraging both MPI and Amazon Trainium. I look forward to your feedback on this proposal.
