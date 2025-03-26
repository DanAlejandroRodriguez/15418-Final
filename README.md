# Parallel K-Means Clustering on Amazon Trainium

**Team:** Daniel Rodriguez (Solo)

**Project URL:** [https://danalejandrorodriguez.github.io/K-means-Clustering-with-Trainium/](https://danalejandrorodriguez.github.io/K-means-Clustering-with-Trainium/)

---

## Summary

We propose to implement a parallel K-Means clustering algorithm that scales to large datasets by leveraging Amazon Trainium for accelerating the compute-intensive distance computations. The project uses MPI for distributed-memory parallelism combined with Trainium’s Neuron SDK to offload critical operations, with the goal of achieving significant speedup and improved clustering efficiency compared to a serial baseline.

---

## Background

K-Means clustering partitions data into \(k\) clusters based on distances between data points and centroids. For very large datasets, a serial implementation becomes a bottleneck due to the repeated computation of distances. In this project, I will develop the serial version entirely from scratch as a baseline and then create a parallel version that distributes data across MPI processes and uses Amazon Trainium to accelerate the inner loops. This approach directly applies concepts from distributed-memory programming, load balancing, and hardware acceleration, which are central themes in 15‑418/15‑618.

---

## The Challenge

Although K-Means is conceptually simple, parallelizing it at scale is nontrivial. Challenges include handling irregular data distributions that lead to load imbalance, synchronizing global centroid updates across MPI processes, and efficiently integrating Trainium to accelerate heavy tensor computations. These factors require careful design to minimize communication overhead and achieve good scalability.

---

## Resources

- **Hardware:** Amazon Trainium instances (via the Neuron SDK) and PSC/GHC cluster nodes.
- **Software:** C/C++ (all implementations are built from scratch), MPI for distributed communication, and performance profiling tools such as perf and TAU.
- **References:** Research papers on parallel K-Means clustering and Trainium optimization techniques, along with course materials from 15‑418/15‑618.

---

## Goals and Deliverables

The primary goal is to develop both a serial and a parallel implementation of K-Means clustering. The serial version, built entirely from scratch, will serve as the baseline. The parallel version will use MPI to distribute the workload and leverage Amazon Trainium to accelerate distance computations. Deliverables include complete source code, detailed performance analysis (with speedup graphs and cache statistics), and a final report along with a poster presentation.

---

## Platform Choice

Amazon Trainium is selected because it is specifically designed to accelerate tensor operations common in machine learning workloads. Its architecture can significantly speed up the inner loop of distance calculations in K-Means, especially when combined with MPI-based distributed processing. This hybrid approach maximizes throughput and scalability for large-scale clustering tasks.

---

## Schedule

| Date Range        | Task Description                                                                                                                                             |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mar 26 - Apr 1    | Finalize project design; implement the serial version of K-Means clustering from scratch as the baseline.                                                    |
| Apr 2 - Apr 8     | Set up the MPI environment; partition the dataset across nodes; integrate initial Trainium-accelerated kernels using the Neuron SDK.                           |
| Apr 9 - Apr 15    | Refine and optimize the distance computation on Trainium; begin collecting performance data with perf and TAU.                                                |
| Apr 16 - Apr 22   | Optimize global centroid updates; reduce communication overhead; profile synchronization and load balancing across MPI processes.                            |
| Apr 23 - Apr 28   | Conduct comprehensive benchmarking; generate detailed performance graphs; prepare the final report and poster for the session on April 29th.                 |

---

This proposal outlines the scope, challenges, and planned deliverables for the project while integrating key parallel systems concepts from 15‑418/15‑618. I look forward to receiving feedback on this proposal.
