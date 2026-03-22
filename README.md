# Assignment 3: Understanding Algorithm Efficiency and Scalability

**Name:** Sai Venkata Bharath Reddy Singareddy

## Overview

This repository contains my work for Assignment 3 on **algorithm efficiency and scalability**.  
The assignment focuses on two main topics:

1. **Randomized Quicksort**
2. **Hashing with Chaining**

The goal of this assignment was not only to implement the required algorithms, but also to study their behavior through both **theoretical analysis** and **empirical testing**.

This repository includes:
- a Colab/Jupyter notebook containing the full implementation, experiments, analysis, and observations
- CSV files containing experimental results
- this README file explaining the process followed, how to run the code, and the main findings

---

## Repository Contents

```text
Assignment3_Algorithm_Efficiency_and_Scalability.ipynb
quicksort_experiment_results.csv
hash_table_growth_results.csv
hash_table_operation_results.csv
README.md
```

> If your notebook file has a different name, update the filename in this README before submission.

---

## Work Completed

### Part 1: Randomized Quicksort Analysis

For the first part of the assignment, I implemented:

- **Randomized Quicksort**, where the pivot is chosen uniformly at random
- **Deterministic Quicksort**, where the first element is always used as the pivot

I then:
- tested both implementations for correctness
- compared their runtime on different types of input
- explained the theoretical average-case time complexity of Randomized Quicksort
- connected the experimental results to the theory

#### Input types used in the comparison
- random arrays
- already sorted arrays
- reverse-sorted arrays
- arrays with repeated elements

---

### Part 2: Hashing with Chaining

For the second part of the assignment, I implemented a **hash table using chaining** for collision resolution.

The implementation supports:
- **Insert**
- **Search**
- **Delete**

I also included:
- a **MAD-style hash function**
- **load factor tracking**
- **dynamic resizing** when the table becomes too full

After implementing the hash table, I analyzed:
- expected search time
- expected insert time
- expected delete time
- the effect of the load factor on performance
- how resizing helps maintain efficiency

I also ran a small experiment to observe:
- load factor growth
- capacity changes during resizing
- operation timing behavior as the table grows

---

## Development Process

One of the main goals of this assignment was to show not only the final code, but also the **process followed**.

### Step 1: Implement the required algorithms
I began by writing the core implementations:
- Randomized Quicksort
- Deterministic Quicksort
- Hash Table with Chaining

While writing the code, I added:
- clear **docstrings**
- inline **comments**
- helper functions where needed

This was done so that the operation and purpose of the code would be easy to follow.

### Step 2: Verify correctness
Before running any experiments, I tested the implementations on small and edge-case inputs.

For Quicksort, I tested:
- empty arrays
- single-element arrays
- sorted arrays
- reverse-sorted arrays
- arrays with repeated elements

For the hash table, I tested:
- insertion of new keys
- updating an existing key
- searching for existing keys
- searching for missing keys
- deleting existing keys
- deleting missing keys
- resizing behavior after multiple insertions

This step helped ensure that the later performance results were based on correct implementations.

### Step 3: Run experiments
After correctness was confirmed, I ran empirical experiments.

For Quicksort, I measured runtime across different input distributions and sizes.

For the hash table, I measured:
- how the load factor changed as elements were inserted
- when resizing occurred
- average insert, search, and delete timing behavior

### Step 4: Write analysis and conclusions
Finally, I connected the experimental results back to the theoretical analysis.

For Randomized Quicksort, I explained why the expected running time is \(O(n \log n)\).

For hashing with chaining, I explained why expected operation time depends on the load factor and why keeping the load factor low is important.

---

## How to Run the Code

### Option 1: Run in Google Colab
This assignment was designed to run well in **Google Colab**.

1. Open Google Colab
2. Upload `Assignment3_Algorithm_Efficiency_and_Scalability.ipynb`
3. Run the notebook cells from top to bottom
4. The notebook will:
   - define the algorithms
   - run correctness tests
   - perform experiments
   - generate result tables and plots
   - save CSV files

### Option 2: Run locally with Jupyter Notebook
If you want to run it locally:

1. Make sure Python 3 is installed
2. Install the required libraries:
   ```bash
   pip install pandas matplotlib
   ```
3. Open Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
4. Open the notebook and run all cells

---

## Required Libraries

The notebook uses the following Python libraries:

- `random`
- `time`
- `sys`
- `pandas`
- `matplotlib`

Some of these are part of the Python standard library.  
`pandas` and `matplotlib` may need installation if running locally.

---

## Summary of Findings

### Randomized Quicksort
The experimental results were consistent with the theory.

- Randomized Quicksort performed more consistently across different input types.
- Deterministic Quicksort using the first element as pivot became much slower on sorted and reverse-sorted arrays.
- This behavior matches the theoretical idea that Randomized Quicksort has expected time complexity \(O(n \log n)\), while Deterministic Quicksort can degrade to \(O(n^2)\) on unfavorable input orders.
- Using three-way partitioning helped handle repeated elements cleanly.

### Hashing with Chaining
The hash table experiments also matched the theoretical expectations.

- Insert, search, and delete remained efficient when the load factor stayed under control.
- As more elements were inserted, the load factor increased until resizing occurred.
- Dynamic resizing increased the number of buckets and helped reduce collision pressure.
- This supports the theoretical result that the expected time for operations with chaining is \(O(1 + \alpha)\), where \(\alpha\) is the load factor.

---

## Notes on Code Quality

To improve code readability and documentation, I made sure that:

- functions include **docstrings**
- important logic includes **inline comments**
- the notebook includes **process explanations**
- observations are written after major experiment sections

This was done intentionally so that the repository documents both the **implementation** and the **reasoning process** behind it.

---

## Output Files

Running the notebook generates the following result files:

- `quicksort_experiment_results.csv`
- `hash_table_growth_results.csv`
- `hash_table_operation_results.csv`

These files contain the recorded measurements used in the analysis.

---

## Conclusion

This assignment helped me compare algorithm behavior from both a theoretical and practical perspective.

The main lessons were:

- Randomization makes Quicksort more robust against bad input orderings.
- A fixed pivot strategy can lead to poor performance in practice.
- Hashing with chaining works well when keys are distributed evenly and the load factor is controlled.
- Dynamic resizing is important for maintaining good average performance as the table grows.

Overall, the assignment showed how implementation details, input structure, and theoretical analysis all work together when evaluating algorithm efficiency and scalability.
