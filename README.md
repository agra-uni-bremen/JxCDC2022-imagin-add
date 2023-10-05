# JxCDC2022-imagin-add

Artifacts of the paper: "IMAGIN: Library of IMPLY and MAGIC NOR Based Approximate Adders for In-Memory Computing"


##Folder Structure

This magic_based folder contains the Pareto-optimal deisgns for MAGIC NOR based approximate adders.

```
|-> 8-bit 
	|-> DesignMetric_ErrorMetric
		|-> NAB-bit 2, 4, and 6 # Number of Approximated bits 
|-> 12-bit 
	|-> DesignMetric_ErrorMetric
                |-> NAB-bit 2, 4, 6, 8, and 10 # Number of Approximated bits
|-> 16-bit 
	|-> DesignMetric_ErrorMetric
                |-> NAB-bit 2, 4, 6, 8, 10, 12, and 14 # Number of Approximated bits
```

Similarly imply_based folder contains the Pareto-optimal designs for the IMPLY based approximate adders.

NOTE: In our paper we did the pareto analysis on all the NAB designs again to obtain the overall Pareto. However we have presented the designs here for separately for all the NABs for better granularity. 

### Subfolder Structure

The Design Metrics used are Time Serial, Time Parallel, Number of Memristor (#using LIST Scheduling), and Energy.The error metrics used are Mean Absolute Error (MAE), Mean Square Error (MSE), and Mean Square Log Error (MSLE). We have a folder for each of the design and error metric. Within each folder the designs are subdivided into the number of approximated bits.

### File Information

ALl the files are in the AIGER (.aig) format. The port mapping is as follows for the 8-bit adder:

	
	INPUT:
	First 8 bits are the operand 1
 	Next 8 bits are the operand 2
	
	Output:
	Next 8 bits are the Sum output 
	Last bits is the Carry output

Example :

	module top (a1,a2,......, a25)
	endmodule 

The ports need to be read as 
	
	operand 1 = {a1,a2,...,a8} LSB to MSB
	operand 2 = {a9,a10,...,a16} LSB to MSB
	Sum  = {a24,a23,...,a17} MSB to LSB
	Carry = {a25}

Please Note:
	Final output of the addition will be formed by concatenating {Carry,Sum}. 
	The inputs are from LSB to MSB unlike SUM output which is from MSB to LSB.
In case you want to use the designs in the conventional manner a top module can be created which does the port mapping for all inputs and outputs from MSB to LSB.
## Citation

To cite this paper use
```bibtex
@ARTICLE{9950064,
  author={Jha, Chandan Kumar and Thangkhiew, Phrangboklang Lyngton and Datta, Kamalika and Drechsler, Rolf},
  journal={IEEE Journal on Exploratory Solid-State Computational Devices and Circuits}, 
  title={IMAGIN: Library of IMPLY and MAGIC NOR-Based Approximate Adders for In-Memory Computing}, 
  year={2022},
  volume={8},
  number={2},
  pages={68-76},
  doi={10.1109/JXCDC.2022.3222015}}
``` 
