Thor Network-on-Chip
====

Thor is a Hermes-based (and improved) NoC implemented in VHDL.  

This repository contains the NoC itself and the input/output modules (in SystemC)
that inject/collect traffic in/from the network.
It also contains TCL scripts to compile and simulate with Modelsim.  

Thor is a highly parameterizable, clean and easy-to-understand implementation.
It's frequently checked for synthesis compliance and is coded in VHDL'93.
## Directory tree
On the root directory there're two folders:
Monitores, which contains the SystemC files that work as testbench for the NoC;
and NoC, which contains the NoC itself and its components.  

On the root are also placed the toplevel architecture that binds the NoC to the
input/output modules.
There'are also the compilation script (comp.do) and
the simulation script (sim.do).
## Parameters/Customization
Thor can be easily customized.
Two files need to be changed in order to accomplish that:
Thor_package.vhd and SC_common.h.
The last one only in the case you change the flit width.  

The parameters are: flit width, input buffers depth and NoC size.  

As Thor uses as routing mechanism tables,
the routing algorithm can also (not so easily) be changed by filling these tables.
All you have to do is follow the RBR codification.
## Simulation
To actually simulate Thor we recommend using the Mentor Graphics Modelsim SE tool
that allows using mixed language (here VHDL+SystemC).
Once you have it, the TCL scripts will do the rest of the work.
### Input files
### Output files
### TCL Scripts
The TCL scripts (comp.do and sim.do) are self explanatory.
The first compiles the NoC and the input/output modules and
the second will actually simulate the assembly. It's passed unlimited
time to the simulation as the output module will detect the arrival of
all packages and automatically fires the simulation end.
## Related Resources
