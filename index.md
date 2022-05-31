## DCP: Learning Accelerator Dataflow for Neural Network via Propagation

We propose an efficient data-centric approach Dataflow Code Propagation (DCP) to automatically find the optimal dataflow for different DNN layers in seconds without human effort.


### Visualization of Propogation process

In this part, we visualize the dataflow propagation process of DCP for the first layer in ResNet101. We visualize the dataflow in three aspects: the target propagation metric, the number of PEs, and memory size for one cluster of the corresponding memory level (e.g., L2, L1, and L0). Three target metrics (e.g., Latency, Energy, and EDP) are selected to perform single objective optimization, and a multiple objectives optimization for latency and energy is also shown here.


#### Multiple objectives optimization (Latency and Energy)

<div align=center><img src="images/multi_latency_energy.png" title="The change of latency and energy in multiple objectives optimization. The arrow indicates the evolution of the performance of propagated dataflow in each step." width="50%"></div>

<div align=center><img src="images/multi_pe.png" title="The change in the number of PEs contained in one L2, L1, and L0 buffer cluster." width="80"></div>

<div align=center><img src="images/multi_memory.png" title="The change of memory size along with propagation epoch. The total on-chip buffer indicates the sum of L2, L1, and L0 buffer."></div>


#### Single objective optimization (Latency)

<div align=center><img src="images/runtime_change.png" title="The change of latency along with the propagation epoch." width="40%"></div>

<div align=center><img src="images/runtime_pe.png" title="The change in the number of PEs contained in one L2, L1, and L0 buffer cluster." width="80"</div>

<div align=center><img src="images/runtime_memory.png" title="The change of memory size along with propagation epoch. The total on-chip buffer indicates the sum of L2, L1, and L0 buffer."></div>


#### Single objective optimization (Energy)

<div align=center><img src="images/energy_change.png" title="The change of energy along with the propagation epoch." width="40%"></div>

<div align=center><img src="images/energy_pe.png" title="The change in the number of PEs contained in one L2, L1, and L0 buffer cluster." width="80"></div>

<div align=center><img src="images/energy_memory.png" title="The change of memory size along with propagation epoch. The total on-chip buffer indicates the sum of L2, L1, and L0 buffer."></div>


#### Single objective optimization (EDP)

<div align=center><img src="images/edp_change.png" title="The change of EDP along with the propagation epoch." width="40%"></div>

<div align=center><img src="images/edp_pe.png" title="The change in the number of PEs contained in one L2, L1, and L0 buffer cluster." width="80"></div>

<div align=center><img src="images/edp_memory.png" title="The change of memory size along with propagation epoch. The total on-chip buffer indicates the sum of L2, L1, and L0 buffer."></div>

