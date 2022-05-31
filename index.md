## DCP: Learning Accelerator Dataflow for Neural Network via Propagation

We propose an efficient data-centric approach Dataflow Code Propagation (DCP) to automatically find the optimal dataflow for different DNN layers in seconds without human effort.


### Visualization of Propogation process

In this part, we visualize the dataflow propagation process of DCP for the first layer in ResNet101. We visualize the dataflow in three aspects: the target propagation metric, the number of PEs, and memory size for one cluster of the corresponding memory level (e.g., L2, L1, and L0). Three target metrics (e.g., Latency, Energy, and EDP) are selected to perform single objective optimization, and a multiple objectives optimization for latency and energy is also shown here.


#### Multiple objectives optimization (Latency and Energy)

<div>
    <center>	
    <img src="images/multi_latency_energy.png"
         style="zoom:80%"/>
    <br>
    The change of latency and energy in multiple objectives optimization. The arrow indicates the evolution of the performance of propagated dataflow in each step. The star labels the performance of the final optimized dataflow.
    </center>
</div>

<br>

<div>
    <center>	
    <img src="images/multi_PE.png"
         style="zoom:20%"/>
    <br>
    The change in the number of PEs contained in one L2, L1, and L0 buffer cluster.
    </center>
</div>

<br>

<div>
    <center>	
    <img src="images/multi_memory.png"
         style="zoom:100%"/>
    <br>
    The change of memory size along with propagation epoch. The total on-chip buffer indicates the sum of L2, L1, and L0 buffer.
    </center>
</div>

<br>

#### Single objective optimization (Latency)

<div>
    <center>	
    <img src="images/runtime_change.png"
         style="zoom:15%"/>
    <br>
    The change of latency along with the propagation epoch.
    </center>
</div>

<br>

<div>
    <center>	
    <img src="images/runtime_PE.png"
         style="zoom:20%"/>
    <br>
    The change in the number of PEs contained in one L2, L1, and L0 buffer cluster.
    </center>
</div>

<br>

<div>
    <center>	
    <img src="images/runtime_memory.png"
         style="zoom:100%"/>
    <br>
    The change of memory size along with propagation epoch. The total on-chip buffer indicates the sum of L2, L1, and L0 buffer.
    </center>
</div>

<br>

#### Single objective optimization (Energy)

<div>
    <center>	
    <img src="images/energy_change.png"
         style="zoom:15%"/>
    <br>
    The change of energy along with the propagation epoch.
    </center>
</div>

<br>

<div>
    <center>	
    <img src="images/energy_PE.png"
         style="zoom:20%"/>
    <br>
    The change in the number of PEs contained in one L2, L1, and L0 buffer cluster.
    </center>
</div>

<br>

<div>
    <center>	
    <img src="images/energy_memory.png"
         style="zoom:100%"/>
    <br>
    The change of memory size along with propagation epoch. The total on-chip buffer indicates the sum of L2, L1, and L0 buffer.
    </center>
</div>

<br>

#### Single objective optimization (EDP)

<div>
    <center>	
    <img src="images/edp_change.png"
         style="zoom:15%"/>
    <br>
    The change of EDP along with the propagation epoch.
    </center>
</div>

<br>

<div>
    <center>	
    <img src="images/edp_PE.png"
         style="zoom:20%"/>
    <br>
    The change in the number of PEs contained in one L2, L1, and L0 buffer cluster.
    </center>
</div>

<br>

<div>
    <center>	
    <img src="images/edp_memory.png"
         style="zoom:100%"/>
    <br>
    The change of memory size along with propagation epoch. The total on-chip buffer indicates the sum of L2, L1, and L0 buffer.
    </center>
</div>

