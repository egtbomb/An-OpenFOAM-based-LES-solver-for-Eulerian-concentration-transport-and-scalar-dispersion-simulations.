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
After executing this command, a new solver named `concenFoam` will be compiled.  
This solver is capable of performing transient turbulent flow simulations coupled with the Eulerian concentration transport equation.

It should be noted that the concentration scalar field in this solver is defined by the variable `T`.

## Synthetic Turbulence Inflow Generation

In the next step, the `CDRFG` utility must be executed in the main case directory in order to generate synthetic turbulent inflow data for the inlet plane over the desired time intervals.

The compilation procedure and complete usage instructions for this utility are fully described in the following repository:
https://github.com/egtbomb/CDRFG-synthetic-turbulence-inflow

- :contentReference[oaicite:0]{index=0}
