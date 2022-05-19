## DCP: Learning Accelerator Dataflow for Neural Network via Propagation

We propose an efficient data-centric approach Dataflow Code Propagation (DCP) to automatically find the optimal dataflow for different DNN layers in seconds without human effort.

### Dataflow
Dataflow is the data communication pattern within a DNN accelerators between the compute and memory elements. Dataflow affects the data reuse pattern, which is critical to throughput and energy efficiency of the accelerator.

#### Motivation
In the process of running DNN application, there are multiple opportunities to reuse data like input tensor reuse, filter weight reuse, which can be leveraged by multicasting. Multicasting means read a data point from a buffer only once and replicates it spatially or temporally. Spatial multicasting means deliver the data point to multiple spatial destinations (PEs) and it can reduce expensive memory access and data transfer to save energy and decrease latency. Temporal multicasting means deliver the data to multiple temporal destinations (same PE at different time stamp) and it has the same functionality just like the spatial multicasting.

***Multicasring.*** In the process of running DNN application, there are multiple opportunities to reuse data like input tensor reuse, filter weight reuse, which can be leveraged by multicasting. Multicasting means read a data point from a buffer only once and replicates it spatially or temporally. Spatial multicasting means deliver the data point to multiple spatial destinations (PEs) and it can reduce expensive memory access and data transfer to save energy and decrease latency. Temporal multicasting means deliver the data to multiple temporal destinations (same PE at different time stamp) and it has the same functionality just like the spatial multicasting.

***Reduction.*** Reduction means accumulates partial outputs spatially or temporally to get the destined output. For example, every output in convolution is the accumulation of multiple partial outputs getting by the multiplication of input tensors and weights. Spatial reduction means accumulate these partial outputs from multiple spatial destinations while temporal reduction means accumulate them from multiple temporal destinations.

#### Expression
In specific, we use three factors to describe a dataflow, which are parallelism, computation order and partitioning size. 

***Parallelism.*** Parallelism is about allocating the computation workload into the multiply hardware processing units and let these processing units can perform the computation simultaneously. For DNN accelerators, the processing units are PEs and it usually achieve parallelism via unrolling the loop nest of convolutional layers spatially.

***Computation order.*** Computation order is the temporal order of the dimensions to be performed in the multiply dimensional computation task. Different computation order can exploit different data movement pattern and data reuse opportunities.

***Partitioning size.*** As there are many parameters to the DNN application and the buffer of DNN accelerators are limited, accelerators with multi-level memory hierarchy will partition these parameters and allocate them into buffer. In this process, partitioning size will determine the data size of each tensor (input/output/weight) that need to be present within the accelerator’s buffer at each time stamp.

#### Example
A simple 1-D convolution and its loop expression is shown in Fig. 1a. The loop shown in Fig. 1b is time-consuming as it only performs one multiplication and one add operation at each time step. If we apply the parallelism to this 1-D conv by unrolling the loop and use three processing elements to perform the computation task simultaneously, the 1-D conv will be performed like it is shown in Fig. 1c. 

<div align=center><img src="images\1-D_conv_parallel.png" width="600" title="Figure 1. The computation process and loop expression of 1-D conv."></div>

Then for the affect of computation order, it is illustrated in Fig. 2. Stationary means the corresponding data stay the longest in accelerator’s buffer. As it is shown in Fig. 2, tmp refers to one data in accelerator’s buffer and different computation order may result in different number of memory access for each tensor. 

<div align=center><img src="images\1-D_conv_stationary.png" width="600" title="Figure 2. Different computation orders for 1-D conv."></div>

As it is shown in Fig. 3, DNN accelerators have a multi-level memory hierarchy and limited size of buffer. Therefore, the data used in DNN applications may need to be partitioned before it has been transferred into the DNN accelerators and perform the computation.

<div align=center><img src="images\1-D_conv_partition.png" width="400" title="Figure 3. Output partition example for 1-D conv."></div>


