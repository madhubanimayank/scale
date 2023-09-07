## Disclaimer : ChatGPT text. It will be edited soon. 
# Input Scaling for Improved Parameter Initialization in QAOA

## Introduction

This project examines the potential impact of input scaling on the cost landscape of the Quantum Approximate Optimization Algorithm (QAOA). The focus is on how input scaling might lead to similar cost landscapes for different instances and how such similarities could benefit parameter initialization in QAOA.

## Objective

The main goals of this project include:

1. Understanding the potential effects of input scaling on the cost landscape of QAOA.
2. Investigating the possibility of using cost landscape similarity for parameter initialization in QAOA.
---
## Methodology

The methodology involves defining a function named `run_qaoa_benchmark`, which takes several parameters to run a QAOA benchmark for the Vehicle Routing Problem (VRP) based on the provided parameters. Below are the input parameters and their descriptions:

1. `distance_matrix` (List[List[float]]): The matrix representing the distances between the locations. It is scaled to the range [0, 1] based on the maximum distance value in the matrix.

2. `n_vehicles` (int): The number of vehicles available for the VRP.

3. `device_location` (str, optional): The location of the simulator. Defaults to 'local'.

4. `device_name` (str, optional): The name of the simulator. Defaults to 'qiskit.qasm_simulator'.

5. `parameter_type` (str, optional): The type of the parameter. Defaults to 'standard'.

6. `initialization_type` (str, optional): The initialization type. Defaults to 'rand'.

7. `mixer_hamiltonian` (str, optional): The mixer Hamiltonian type. Defaults to 'x'.

8. `n_shots` (int, optional): The number of shots for the device. Defaults to 85.

Using the input parameters, the function performs the following steps:

1. A VRP instance is created using the distance matrix and the specified number of vehicles.

2. A QAOA instance is created, and the backend and circuit properties are set.

3. The QAOA instance is compiled with the QUBO representation of the VRP instance.

4. A QAOA benchmark is run using the compiled QAOA instance, and the results are displayed as a plot.

All input parameters can be altered to run the QAOA benchmark with different settings.

The function is further modified to create a new version to do scaling before the benchmark. 
Currently, various distance matrices are compared for corresponding cost landscape similarity. 


## Dependencies

The following Python packages are necessary for this project:

- `networkx`: For graph-based structures.
- `numpy`: For numerical operations.
- `qiskit`: For quantum circuit simulation as well as execution on real devices.
- `openqaoa`: For quantum optimization problems and QAOA benchmarking.

These dependencies can be installed using `pip`:

```bash
pip install networkx numpy matplotlib openqaoa
```

## Usage

1. Clone the repository:

```bash
git clone https://github.com/madhubanimayank/SCALED_OPTIMIZATION.git
```

2. Navigate to the project directory:

```bash
cd SCALED_OPTIMIZATION
```

3. Run the Jupyter notebook:

```bash
jupyter notebook notebook.ipynb
```

4. Execute the cells in the notebook to run the experiments.

## Results

The experiments have shown that input scaling to the range [0, 1] can lead to increased similarity in the cost landscapes for different distance matrices. Applying the same penalty value further enhances this similarity. Exploration is underway to determine how this similarity might be used for parameter initialization in QAOA, potentially leading to improved optimization performance for new instances.

Detailed results and visualizations can be found in the Jupyter notebook.

## Conclusion

Input scaling and applying a constant penalty for each instance seem to be a promising approach for improving parameter initialization in QAOA, as they make cost landscapes more similar for different instances, which could assist with the initialization of parameters for new instances and potentially enhance the optimization performance of QAOA.
## Future Work

More details about parameter initialization based on the observed similarities in the cost landscapes are being prepared. Future research might explore different scaling techniques, the impact of penalty values, and the effects of input scaling on the optimization performance of QAOA for other problems.

## Acknowledgments

Gratitude is extended to the authors of the `openqaoa` package for providing an open-access to the package . This package was used to run QAOA benchmarks in the experiments.
