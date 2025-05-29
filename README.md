
# Parallel HyperLogLog Cardinality Estimation 📊

This project demonstrates how to estimate the cardinality (i.e., the number of unique elements) of dataset columns using the **HyperLogLog (HLL)** algorithm with parallel processing for improved performance.

## Overview 🚀

The script loads a transactional dataset, cleans and standardizes it, and then estimates the number of unique elements in selected columns using HyperLogLog sketches, which are computed in parallel using Python's `multiprocessing` module.

## Features ✨
- Data cleaning: removing duplicates and missing values
- Standardizing numeric columns (`Quantity` and `UnitPrice`)
- Visualizing dataset statistics and aggregated customer data
- Estimating cardinality with HyperLogLog using multiple processes
- Comparing performance with different numbers of processes
- Comparing estimated cardinality against actual unique counts

## Requirements 🧰

- Python 3.7+
- Required libraries:
  - pandas
  - numpy
  - matplotlib
  - scikit-learn
  - hyperloglog

📦 Install dependencies via pip:

```bash
pip install pandas numpy matplotlib scikit-learn hyperloglog
```

## Usage 📋

1. Download the dataset file `data.csv` from this link and place it in the same directory as the script:  
   [Dataset on Google Drive](https://drive.google.com/drive/folders/12ws6gycNK6g2d_exvBIYzRAokSc0Um5P?usp=sharing)

2. Clone the repository:

```bash
git clone https://github.com/20101301-Alina-Hasan/Parallel-HyperLogLog.git
cd Parallel-HyperLogLog
```

3. Run the script:

```bash
python parallel-hyperloglog.py
```

4. The script will output dataset info, statistics, plots, cardinality estimation results, and save the processed data as `updated_dataset.csv`

## How It Works 🔧

- The dataset is cleaned by dropping duplicates and missing values.
- Numeric columns are standardized using z-score normalization.
- Data is partitioned, and each partition is processed in parallel to build partial HyperLogLog sketches.
- Partial sketches are merged to produce an overall cardinality estimate.
- Execution time is measured for different numbers of processes to demonstrate speedup.
- Results are visualized and printed for easy comparison.

## Visualization 📈

- Frequency of top countries in the dataset
- Aggregated customer data trends (StockCode counts, Quantity sums, UnitPrice means)
- Time taken to estimate cardinality vs number of processes
- Bar plots comparing actual unique counts to estimated cardinalities
- Scaled absolute difference between actual and estimated cardinalities per column

## Notes 📝

- The HyperLogLog error rate is set to 1% (`error_rate=0.01`).
- Parallelization improves performance on large datasets but overhead may limit gains beyond a certain number of processes.

## Contributing 🙌 

Contributions are welcome! If you have suggestions or want to collaborate, feel free to open an issue or pull request.

## Contact 📧 

For questions or inquiries, reach out via alina.hasan@g.bracu.ac.bd

---

Feel free to ⭐ the repo if you find it useful.
