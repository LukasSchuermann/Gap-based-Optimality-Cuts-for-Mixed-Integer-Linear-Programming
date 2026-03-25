# Gap-based Optimality Cuts for Mixed-Integer Linear Programming

This project contains the implementation of the GO cuts separator for MILPs used for the paper "Gap-based Optimality Cuts for Mixed-Integer Linear
Programming"
It is implemented in C++ using the MINLP solver SCIP.

## Requirements

To run this codes you need an installation of SCIP (we used version 9.1.1). Env_Variable "SCIP_DIR" shall contain the path to the SCIP installation.
See the website for an installation guide:
https://scipopt.org/#scipoptsuite

Afterwards, either open the directory mixed-integer or pure-integer and execute the following lines to build the binary
```markdown
$ mkdir build
$ cd build
$ cmake .. -DSCIP_DIR="/path/to/scip/installation"
$ make
```
Now we can run the code as in the following example:
```markdown
$ ./go ../../instances/pure_integer/irp.mps +useCutting
```
## Replication of the results
To replicate the results from the paper, load the corresponding settings via "+settings set-x"
Root node experiment: *root-mir* or *root-pure*
Branch-and-cut experiment: *mir* or *pure*

For both experiments we used seeds 0-9.

Example:
```markdown
$ ./go ../../instances/pure_integer/irp.mps +useCutting +settings pure-int +seed 0
```
