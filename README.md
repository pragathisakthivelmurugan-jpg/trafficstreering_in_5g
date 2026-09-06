# 5G Open RAN Dynamic Traffic Steering Simulator

An execution framework designed to simulate, visualize, and analyze intelligent **Traffic Steering** algorithms within an open and virtualized **5G Radio Access Network (Open RAN)** topology.

---

## 📖 System Operational Design

The simulation script architectures a spatial topology network to map out two core deployment execution paradigms controlled by an optimized **Near-Real-Time RAN Intelligent Controller (Near-RT RIC)**:

### Scenario A: BEFORE Steering (Unoptimized Shortest-Path Mode)
* **Logic:** User Equipment (UE) devices hook blindly to base stations (`gNB Nodes`) based solely on spatial closeness (Minimum Euclidean Distance Path).
* **Bottleneck:** Because spatial demand density is concentrated unevenly, **Cell 3 suffers a severe traffic overload bottleneck**, while adjacent base stations remain heavily underutilized. This state introduces extreme queue delay latency and threatens Quality of Service (QoS) drop bounds.

### Scenario B: AFTER Steering (Open RAN Load-Balanced Mode)
* **Logic:** An optimization loop mimicking a micro-service framework (**xApp**) running on the Near-RT RIC actively samples queue load levels. 
* **Mitigation:** When Cell 3 breaches its `capacity_threshold` (120 Mbps), the engine intercepts boundary connection states and seamlessly **steers 33% of the congested user paths** to the next-best available neighbor base station runner-up, balancing the entire network grid.

---

## 📊 Dynamic Metrics Calculated

Rather than utilizing static values, all log analytics generated in the console stream are evaluated live based on the running network layout matrices:
* **Average Latency:** Derived dynamically per-user based on connection distance vectors (propagation time) plus base station loading volumes (queuing delay overhead).
* **Total Power Usage:** Calculated live via a fixed baseline power configuration (15.0 Watts per cell site) aggregated with a variable traffic load coefficient (0.12 Watts per processed Mbps).
* **User Scalability Analysis:** Computes finite cell bandwidth splitting arrays to model exponential data-rate decay per user alongside dynamic system capacity variations under device density stress tests.

---

## 🛠️ Execution Instructions

### Prerequisites
The script runs completely on standard, lightweight Python scientific computation toolkits. It supports environment paths from Python 3.11 up to Python 3.14 without requiring heavy engine dependencies like TensorFlow:

```bash
pip install numpy matplotlib
```

### Running the Simulator
To train the allocation matrices, trace connection paths, and trigger visual plotting windows, execute the script via your workspace terminal terminal launcher:
```bash
python oran5g.py
```

---

## 📈 Visual Figures Rendered

Upon successful execution, the script generates two clean figure panels:
1. **Figure 1 (Before vs. After Tracking Map):** Displays a side-by-side geographic visualization layout. The left pane flags the high-congestion connection footprint at Cell 3, while the right pane illustrates balanced user connection boundary assignments.
2. **Figure 2 (Capacity & Throughput Graphs):** A multi-panel engineering chart tracking data-rate split curves alongside fluctuating system resilience waves over heavy user scaling counts.
