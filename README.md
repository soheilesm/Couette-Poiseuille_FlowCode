# Couette-Poiseuille Flow Code  
[![DOI](https://zenodo.org/badge/125785403.svg)](https://zenodo.org/badge/latestdoi/125785403) [![HitCount](http://hits.dwyl.io/aakash30jan/Couette-Poiseuille_FlowCode.svg)](http://hits.dwyl.io/aakash30jan/Couette-Poiseuille_FlowCode)


The work on computations of Couette-Poiseuille flow with a mixing-length model was done as of part of `Turbulence Practices - Individual Research Project (8 ECTS)` course supervised by [Dr. Jean-Philippe Laval](http://imp-turbulence.ec-lille.fr/Webpage/Laval/) during the  coursework of Master's Program in Turbulence. The objective of this course was to program a turbulent model in a simple case and to compare the results with the theoretical solution in laminar case, and with experimental results for the turbulent case. As the case was simple, the effect of several parameters such as the number of grid point as well as the grid stretching near the wall were investigated. The attached [report](https://github.com/aakash30jan/Couette-Poiseuille_FlowCode/raw/master/PatilAakash_Report_CPFlow.pdf) contains the details of the case investigated, the governing equations, the details of computation code as well as discussions on the results obtained.


## Directory Structure:
```sh
cpFlow
├── README.md
├── src
│   ├── autoplotting.py
│   ├── cpFlow.f90
│   ├── Makefile
│   ├── module_grid.f90
│   ├── module_parameters.f90
│   ├── module_solver.f90
│   └── module_triSolve.f90
│
├── Experimental_Data
│   ├── <Casewise Experimental Data>
│   ├── cleanUp.sh
│   └── Experimental_Data_Backup.zip
│
├── Generated_Plots
│   ├── <NEW AUTO-PLOTS WOULD COME HERE>
│   └── plots_previousRun
│       └──<Casewise Comparison Plots>
│
└──  Simulated_Data
    ├── <NEW DATA FILES WOULD COME HERE>
    └── dataFiles_previousRun
       └── <Casewise Simulation Data>
```


## Requirements:
1. gfortran 4.8.4+
2. python 2.7 (optional)
3. numpy 2.1.0+ (optional)
4. matplotlib 1.13.1+ (optional)
5. optparse 1.5.3+ (optional)

## Download
Clone the repository with all the development phase data by:  
`$ git clone https://github.com/aakash30jan/Couette-Poiseuille_FlowCode.git`  
OR  
Get the published source-code tarball by:  
`$ wget https://github.com/aakash30jan/Couette-Poiseuille_FlowCode/blob/master/cpFlow.tar?raw=true -O cpFlow.tar`  
OR  
[Click Here](https://github.com/aakash30jan/Couette-Poiseuille_FlowCode/blob/master/cpFlow.tar?raw=true) to directly download the published source-code tarball. 

## Build:
1. Extract `cpFlow.tar`
2. Please do not modify the directory structure
3. Navigate to `src`
4. Build with `make`
5. Use `make clean` to clean previous build, if required

## Execution
1. After successfull build, execute `./cpFlow.exe`
2. Navigate to `../Simulated_Data` directory to check the generated data.
3. If auto-plotting was enabled, the plot can be found by navigating to `../Generated_Plots` directory.
        

## Notes:
1. To enable auto-plotting(from `parameters.f90`), Python 2.7 along with the mentioned libraries are required
2. `cleanUp.sh` in the Experimental Data directory is a bash script to rename the original data files and make it python-friendly

## Example Output:
```sh
 ########################################
 ###### Couette_Poiseuille-FlowCode #####
 ########################################
 Please Enter a Case Number(from 1 to 18): 15
 ### Fetching Values from the Parameters File ###
 The selected CASE NUMBER is           15
 Here, the values of VW, H, DPDX are    0.0000000000000000        6.5999999642372131E-002  -13.140000343322754      respectively.
 The data generated will be saved to file Case_15_sim.dat
 ### Generating Grid ###
 Grid Generation Successfull.
 ### Solving for Flow Parameters ###
 Total Number Iterations =        4330
 UTAU1=  0.65729164581967581      UTAU2=  0.65970274388959960
 UAVG=   12.590156180227595      UMAX=   13.807000589282906
 ### Organizing Data Files ###
 Copied Successfully 
 Copying Generated simulation data to the directory '../Simulated_Data'
 cp Case_15_sim.dat ../Simulated_Data/Case_15_sim.dat
 Copied Successfully 
 ### Plotting ###
 Creating Plots
 python autoplotting.py --file Case_15_sim.dat
 Case to be plotted:  Case_15_
 Plotting Case
 Saving Plots
 Cleaning Execution Directory
```
## Screenshot
<p align="center">
  <img src="./dev/screenshot.png" alt="Screenshot"
       width="750" height="450">
</p>
       
## Cite  
Please use `https://doi.org/10.5281/zenodo.1421983` for citing this code or report. You may also download [this](https://github.com/aakash30jan/Couette-Poiseuille_FlowCode/raw/master/patil_codereport2018.bib) `.bib` file .  

## License
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

