# Project 4: Differential Privacy

## Overview

This project explores and compares three methods for computing the average of integer values with different levels of privacy protection and differential privacy mechanism. 
The goal is to understand the computational trade-offs between no-protection (plain averaging), 
additively homomorphic encryption using the Paillier scheme, multiparty computation using Shamir’s Secret Sharing, and differential privacy mechanism defined in class.

## Requirements

- Python 3.8 or higher
- Jupyter Notebook
- `matplotlib`
- `numpy`
- `phe`
- `csv`
- `time`
- `random`

You can install all dependencies using:
```bash
pip install numpy matplotlib phe csv time random
```

## Actual project files

```
project3/       
├── test.ipynb             
├── runtime_results.csv   
├── avg_results.csv  
└── README.md              
```
- `test.ipynb`: Main notebook that implements all three schemes, runs experiments, and generates graphs.
- `runtime_results.csv`: Saved results from the latest experiment (average runtimes in milliseconds).
- `README.md`: Documentation and instructions for running and interpreting the project.

## How It Works

- **Plain (No Privacy)**: Directly computes the arithmetic mean using Python’s built-in operations.
- **Paillier Encryption**: Encrypts each value using an additively homomorphic cryptosystem; 
  encrypted values are combined and then decrypted to reveal the average.
- **Shamir’s Secret Sharing**: Distributes each secret as polynomial shares among `n` parties, then reconstructs the sum and computes the average using modular arithmetic.
- **Differential Privacy**: a mechanism that adds a laplacian noise using the sensitivity level and privacy budget to guarantee the desired level of privacy.

##  How to run the experiments
 - Open `test.ipynb` in Jupyter and click "Run All". Expected full run time: ~30 mins (for current settings).

## Runtime Observation & Results

The runtime results show that:
- **Plain averaging** is almost instantaneous since it performs simple addition and division.
- **Shamir’s Secret Sharing** is the slowest method compared to the other three as n increases.
- **Paillier Encryption** is faster than Shamir in the current settings. However, for different bits length Paillier could be really slow.
- **Differential Privacy** is really fast, but slower than plain average. This is because the computation doesn't involve any prime number calculation or mod.

The y-axis of the runtime graph is plotted in logarithmic scale to clearly show all three curves.

The encryption, decryption/reconstruction, and computation results show that:
- **Shamir’s Secret Sharing** is slower for larger value of n.
- **Paillier Encryption** is slower for smaller n but faster than Shamir for larger value of n.

The accuracy results show that:
- **Plain averaging** 0 as desired since we did not add any noise to the data.
- **Shamir’s Secret Sharing** same as plain.
- **Paillier Encryption** same as plain.
- **Differential Privacy** is fluctated since we add a laplacian noise in the data.

# Data-Privacy-Project-4

