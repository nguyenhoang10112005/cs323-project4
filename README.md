# Project 3: Secret Sharing

## Overview

This project explores and compares three methods for computing the average of integer values with different levels of privacy protection. 
The goal is to understand the computational trade-offs between no-protection (plain averaging), 
additively homomorphic encryption using the Paillier scheme, and multiparty computation using Shamir’s Secret Sharing.

## Requirements

- Python 3.8 or higher
- Jupyter Notebook
- `matplotlib`
- `numpy`
- `phe`

You can install all dependencies using:
```bash
pip install numpy matplotlib sympy phe
```

## Actual project files

```
project3/       
├── test.ipynb             
├── runtime_results.csv    
└── README.md              
```
- `test.ipynb`: Main notebook that implements all three schemes, runs experiments, and generates graphs.
- `runtime_results.csv`: Saved results from the latest experiment (average runtimes in milliseconds).
- `README.md`: Documentation and instructions for running and interpreting the project.

## How It Works

- **Plain (No Privacy)**: Directly computes the arithmetic mean using Python’s built-in operations.
- **Paillier Encryption**: Encrypts each value using an additively homomorphic cryptosystem; 
  encrypted values are combined and then decrypted to reveal the average.
- **Shamir’s Secret Sharing**: Distributes each secret as polynomial shares among `n` parties, 
  then reconstructs the sum and computes the average using modular arithmetic.

##  How to run the experiments
 - Open `test.ipynb` in Jupyter and click "Run All". Expected full run time: 5 mins (for current settings).

## Runtime Observation & Results

The runtime results show that:
- **Plain averaging** is almost instantaneous since it performs simple addition and division.
- **Shamir’s Secret Sharing** introduces small overhead due to modular arithmetic but remains fast.
- **Paillier Encryption** is significantly slower because it relies on large-number modular exponentiation during encryption and decryption.

The y-axis of the runtime graph is plotted in logarithmic scale to clearly show all three curves.

# Data-Privacy-Project-3
# cs323-project4
