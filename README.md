# An-OpenFOAM-based-LES-solver-for-Eulerian-concentration-transport-and-scalar-dispersion-simulations.
OpenFOAM solver for Large Eddy Simulation (LES) coupled with Eulerian concentration equations, using the CDRFG method for turbulent LES inflow generation.
## Case Files

An OpenFOAM simulation case is included with this repository.  
A coarse background mesh corresponding to the geometry has been uploaded due to its relatively small size. Therefore, mesh generation is not required before running the case.

## Compilation

Before running the simulation, the solver modifications related to the Eulerian concentration equation must be compiled.

To compile the code:

1. Enter the source code directory.
2. Open a terminal in that directory with the OpenFOAM environment loaded.
3. Run the following command:

```bash
wmake
