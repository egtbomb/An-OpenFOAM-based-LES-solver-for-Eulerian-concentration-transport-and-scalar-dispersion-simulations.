# OpenFOAM-LES-EulerianConcentration
An OpenFOAM simulation case is included with this repository.  
A coarse background mesh corresponding to the geometry has been uploaded due to its relatively small size. Therefore, mesh generation is not required before running the case.
The case files contain the simulation results at a specific time step along with all settings applied for the solution process. If rerunning the case is required, follow the instructions below.

# Compilation
### Requirements
* OpenFOAM, preferably v8

The code provided was written for OpenFoam version 8 and requires modifications for use in higher versions of the software.
### Build from source
Before running the simulation, the solver modifications related to the Eulerian concentration equation must be compiled.

* Clone the code to your computer:
* In the lesEulerianConcentration/concenFoamCode directory, it is necessary to compile the solver code that couples the turbulent flow equations with the Eulerian concentration equation
* Compile the code using the following commands:
  
          $ cd $FOAM_UTILITIES/lesEulerianConcentration/concenFoamCode
  
          $ ./Allwclean

          $ ./Allwmake

 A solver named concenFoam is now available for the simultaneous transient solution of the turbulence and concentration equations.

# CDRFG inlet turbulence generator

It is necessary to execute the CDRFG utility in the main project directory in order to generate the inlet flow field as a function of time and space for the inlet boundary. The compilation and usage procedure of this code is presented in Ref. [1].

After executing the above code, directories containing the generated velocity fields at the specified time intervals are created in the constant/boundaryData/inlet folder. During the simulation run, these velocity fields are read sequentially.



### Excuting the  case


* Decompose the case:

           $ decomposePar

*  Finally run the LES case:

          $ mpirun -np 4 consenFoam -parallel
np denotes the number of processor cores used for parallel computation.
# Reference
[1]	https://github.com/egtbomb/CDRFG-synthetic-turbulence-inflow


