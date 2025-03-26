# Parallel K-Means Clustering on Amazon Trainium

**Team:** Daniel Rodriguez (Solo)

**Project URL:** [https://danalejandrorodriguez.github.io/K-means-Clustering-with-Trainium/](https://danalejandrorodriguez.github.io/K-means-Clustering-with-Trainium/)

---

## Summary

In this project, I will develop a parallel implementation of the K-Means clustering algorithm designed to efficiently process large-scale datasets. The project leverages Amazon Trainium for accelerating compute-intensive operations and uses distributed-memory parallelism to scale across multiple nodes. The focus is on achieving high performance and scalability while maintaining clustering accuracy.

---

## Background

K-Means clustering is a fundamental unsupervised learning algorithm used in various application domains, such as market segmentation, image processing, and recommendation systems. With the growing size of datasets in machine learning and data analytics, a single-threaded K-Means algorithm can become a major performance bottleneck. By parallelizing the algorithm, we aim to reduce execution time significantly and enable clustering on datasets that were previously intractable.

This project will work with large, synthetic, and real-world datasets to benchmark the performance improvements. The algorithm will be implemented using distributed-memory programming, allowing multiple nodes to cooperate in clustering data points. Amazon Trainium, a dedicated hardware accelerator for machine learning, will be utilized to speed up the most compute-intensive parts of the algorithm.

---

## The Challenge

Clustering large-scale data poses several challenges:
- **Irregular Data Access:** The K-Means algorithm must compute distances between data points and cluster centroids, which can lead to non-uniform memory access patterns.
- **Communication Overhead:** Aggregating and synchronizing cluster centroids across distributed nodes requires efficient communication, especially as the number of processes increases.
- **Scalability:** Balancing the workload across multiple nodes and leveraging the capabilities of Amazon Trainium for acceleration is nontrivial and requires careful integration of different parallel systems.
  
By addressing these challenges, the project will offer insights into the performance limits of parallel clustering algorithms and the benefits of using specialized hardware.

---

## Resources

- **Hardware:** Amazon Trainium instances (via the Neuron SDK) and access to a distributed computing cluster (e.g., PSC machines or similar).
- **Software:** C/C++ for implementation, MPI for distributed communication, and performance profiling tools such as perf and TAU.
- **Reference Materials:** Research papers on parallel K-Means clustering and relevant sections from the 15-418/15-618 course materials on MPI communication, synchronization, and load balancing.

---

## Goals and Deliverables

- **Primary Goals:**
  - Develop a working parallel K-Means clustering algorithm that leverages both distributed-memory parallelism and Amazon Trainium acceleration.
  - Achieve significant speedup and scalability compared to a serial baseline.
  - Validate clustering accuracy and performance on both synthetic and real-world datasets.

- **Secondary Goals:**
  - Produce detailed performance analyses and scalability graphs (e.g., speedup, communication overhead).
  - Document the impact of different parameters (such as dataset size and process count) on runtime and clustering quality.
  - Prepare a final report and poster summarizing the methodology, experimental results, and conclusions.

---

## Platform Choice

Amazon Trainium is selected for this project because it is specifically designed to accelerate machine learning workloads. Its architecture provides optimized tensor operations, which can greatly benefit the computation-heavy portions of the K-Means algorithm. Combined with MPI-based distributed processing, this platform allows for scalable parallelism that is well suited for large-scale data clustering tasks.

---

## Schedule

**Week 1:**
- Finalize the project proposal and design the overall system architecture.
- Identify suitable datasets and review relevant literature on parallel K-Means clustering.

**Week 2:**
- Implement the basic serial version of K-Means clustering.
- Set up the distributed computing environment and integrate MPI for data partitioning.

**Week 3:**
- Develop and integrate Amazon Trainium acceleration for the compute-intensive portions.
- Begin testing and collecting performance data (using perf and TAU).

**Week 4:**
- Optimize the implementation and conduct extensive scalability tests.
- Analyze experimental results, generate graphs, and prepare the final report and poster.

---

This project is designed to be both challenging and educational, aligning with the core themes of the 15-418/15-618 course, including parallel algorithm design, communication overhead, and performance profiling. I look forward to your feedback on this proposal.

