

</head>
<body>
  <header>
    <h1>Parallel Graph Neural Network Training on Amazon Trainium</h1>
    <p>Daniel Rodriguez (Solo)</p>
  </header>
  
  <section>
    <h2>Webpage URL</h2>
    <p><a href="https://danalejandrorodriguez.github.io/15418-Final/" target="_blank">https://danalejandrorodriguez.github.io/15418-Final/</a></p>
  </section>
  
  <section>
    <h2>Summary</h2>
    <p>
      Our objective is to design and implement a parallel Graph Neural Network (GNN) training framework that leverages Amazon Trainium via the Neuron SDK to accelerate compute-intensive operations, such as feature propagation and gradient computations. The project utilizes MPI for distributed-memory parallelism and aims to achieve significant speedup and scalability on large graph datasets while maintaining model accuracy.
    </p>
  </section>
  
  <section>
    <h2>Background</h2>
    <p>
      Graph Neural Networks (GNNs) are powerful models for learning on graph-structured data with applications in social network analysis, recommendation systems, and bioinformatics. However, training GNNs on large-scale graphs is challenging due to irregular data structures and complex neighbor aggregation operations. In this project, I will build a serial baseline for GNN training from scratch and then develop a parallel version that partitions the graph across MPI processes. Critical tensor operations during feature propagation will be accelerated using Amazon Trainium, aligning with advanced parallel systems concepts from 15‑418/15‑618.
    </p>
  </section>
  
  <section>
    <h2>The Challenge</h2>
    <p>
      Parallelizing GNN training is challenging because of the irregularity in graph data, which can lead to load imbalances and unpredictable communication patterns. Global updates—such as aggregating node features and computing gradients—require careful synchronization to avoid stalling parallel processes. Moreover, integrating Amazon Trainium to accelerate compute-intensive operations demands efficient data transfers and overlap between computation and communication. These factors make achieving scalable performance nontrivial.
    </p>
  </section>
  
  <section>
    <h2>Resources</h2>
    <ul>
      <li><strong>Hardware:</strong> Amazon Trainium instances (via the Neuron SDK) and PSC/GHC cluster nodes.</li>
      <li><strong>Software:</strong> C/C++ (developed from scratch), MPI for distributed communication, and performance profiling tools such as perf and TAU.</li>
      <li><strong>References:</strong> Research papers on parallel GNN training and Trainium optimization, and 15‑418/15‑618 course materials.</li>
    </ul>
  </section>
  
  <section>
    <h2>Goals and Deliverables</h2>
    <p>
      The primary goal is to develop both a serial and a parallel implementation of a GNN training algorithm. The serial version, built entirely from scratch, will serve as the baseline. The parallel version will distribute the graph workload using MPI and leverage Amazon Trainium to accelerate key operations. Deliverables include fully documented source code, detailed performance analysis (with speedup graphs and cache statistics), and a final report along with a poster and live demo.
    </p>
  </section>
  
  <section>
    <h2>Platform Choice</h2>
    <p>
      Amazon Trainium is chosen for its architecture optimized for tensor operations common in deep learning workloads. Combined with MPI-based distributed processing, it is ideal for accelerating the compute-intensive parts of GNN training. The project will be implemented in C/C++ using MPI and the Neuron SDK, ensuring robust and scalable performance.
    </p>
  </section>
  
  <section>
    <h2>Schedule</h2>
    <table>
      <tr>
        <th>Date Range</th>
        <th>Task Description</th>
      </tr>
      <tr>
        <td>Mar 26 -- Apr 1</td>
        <td>Finalize project design and prepare this proposal; implement the serial GNN training algorithm from scratch as the baseline.</td>
      </tr>
      <tr>
        <td>Apr 2 -- Apr 8</td>
        <td>Set up the MPI environment and partition the graph data; integrate initial Trainium kernels using the Neuron SDK.</td>
      </tr>
      <tr>
        <td>Apr 9 -- Apr 15</td>
        <td>Refine and optimize Trainium-accelerated feature propagation and gradient computations; begin collecting performance data using perf and TAU.</td>
      </tr>
      <tr>
        <td>Apr 16 -- Apr 22</td>
        <td>Optimize global aggregation routines and reduce communication overhead; profile synchronization and load balancing across MPI processes.</td>
      </tr>
      <tr>
        <td>Apr 23 -- Apr 28</td>
        <td>Conduct comprehensive benchmarking; generate performance graphs; prepare the final report and poster for the presentation on Apr 29.</td>
      </tr>
    </table>
  </section>
  
  <footer>
    <p>© 2025 Daniel Rodriguez. All rights reserved.</p>
  </footer>
</body>
</html>
