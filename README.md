# Quantum Diffraction Simulation

**Authors:**  
Cecilie S. Rønnestad & Vaitian L. Marianayagam

Numerical simulation of quantum diffraction using the two-dimensional, time-dependent Schrödinger equation.
The project models a Gaussian wave packet propagating through single-, double- and multi-slit potentials,
and analyses the resulting probability distributions.
The simulation is implemented in C++ using the Crank-Nicolson method and Python tools are used for post-processing and visualization.


## Project structure

- `src/` – C++ implementation of the numerical solver  
- `include/` – Header files  
- `params/` – Input parameter files for simulation setup  
- `python/` – Post-processing and plotting scripts  
- `animation/` – Example animation of simulation results  




## Build and run

### 1) Generate a parameter file (`set_params.cpp`)

`set_params.cpp` creates an input parameter file for the simulation.  

**Build**
```bash
g++ set_params.cpp -larmadillo -o set_params.exe
```

**Run**
```bash
./set_params.exe
```

### 2) Compile the simulation
**Build**
```bash
g++ main.cpp src/Quantum_box.cpp -I include -larmadillo -o main.exe
```


### 3) Run the simulation
```bash
./main.exe params/<input_filename.txt> files/<output_filename.bin> <track deviation [true/false]>
```

The output file is a binary Armadillo object containing the wave function over time. If track_deviation is set to true, 
an additional file named deviation.bin is created.
It contains a complex vector with the deviation of total probability from 1 over time.











