
# Parallelizing HyperLogLog for Scalable Cardinality Estimation 📊

This project demonstrates how to estimate the cardinality (i.e., the number of unique elements) of dataset columns using the **HyperLogLog (HLL)** algorithm with parallel processing for improved performance.

## Overview 🚀

This project demonstrates how to estimate the cardinality (i.e., the number of unique elements) of dataset columns using the **HyperLogLog (HLL)** algorithm with parallel processing for improved performance.
📄 **Read the full research documentation here**: [Parallelizing HyperLogLog for Scalable Cardinality Estimation](Parallel%20HyperLogLog%20For%20Scalable%20Cardinality%20Estimation.md)

The example dataset used is a **transactional dataset** containing **54,190 entries** with columns such as `InvoiceNo`, `StockCode`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, and `Country`. This dataset is first cleaned by removing duplicate and missing rows, and numeric columns like `Quantity` and `UnitPrice` are standardized using z-score normalization.

The script performs exploratory data analysis by visualizing the most frequent countries and aggregated customer purchase behaviors. Then, it estimates the number of unique elements in selected columns using HyperLogLog sketches, which are computed in parallel with Python's `multiprocessing` module for faster execution.

While this example uses a transactional dataset, the approach can be applied to **any large dataset** where estimating unique counts efficiently is required.

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
git clone https://github.com/20101301-Alina-Hasan/Parallel-HyperLogLog-Cardinality-Estimation.git
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
- Parallelization improves performance on large datasets, but overhead may limit gains beyond a certain number of processes.

## Contributing 🙌 

Contributions are welcome! If you have suggestions or want to collaborate, feel free to open an issue or pull request.

## Contact 📧 

For questions or inquiries, reach out via alina.hasan@g.bracu.ac.bd

---

Feel free to ⭐ the repo if you find it useful.
