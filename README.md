# 🧪 Exploratory Data Analysis of the PubChem Chemical Space

## 📌 Project Overview
This project presents an end-to-end data analytics pipeline focused on exploring and cleaning a large-scale chemical dataset from the PubChem database. The goal is to extract valuable insights regarding the physical and chemical properties of nearly 2 million compounds, assess their drug-likeness, and apply business analytics frameworks (like ABC analysis) to chemical structures.

This repository serves as a demonstration of working with **domain-specific big data**, handling complex file formats, and deriving statistical insights.

## 🎯 Key Objectives & Analytical Steps
1. **Data Parsing & Extraction:**
   - Parsed raw compressed `.sdf.gz` files containing millions of chemical structures.
   - Extracted key physicochemical descriptors (Molecular Weight, LogP, H-Bond Donors, H-Bond Acceptors) using the `RDKit` cheminformatics library.
2. **Data Quality & Cleaning:**
   - Handled missing values (NaNs) and eliminated full duplicates to maintain statistical integrity.
   - Performed extreme outlier detection (e.g., negative mass, macrocycles).
3. **Statistical Analysis & Visualization:**
   - Evaluated the distribution shapes (Skewness and Kurtosis) of molecular weights.
   - Applied the **3-Sigma Rule (Z-score)** to identify and flag mathematical anomalies without destroying the "Single Source of Truth".
   - Built a correlation matrix to check for multicollinearity among descriptors.
   - Created optimized, high-density scatter plots and boxplots (using `Seaborn`) to solve the overplotting problem typical for 2M+ row datasets.
4. **Business Logic & Drug-Likeness:**
   - Assessed theoretical oral bioavailability by applying Canonical and Realistic **Lipinski's Rule of Five**.
   - Conducted an **ABC Analysis (Pareto Principle)** to evaluate the mass distribution homogeneity within the chemical database.

## 📊 Key Findings
* **Drug-likeness:** A significant portion of the dataset conforms to the realistic Lipinski rules, making them viable candidates for virtual screening.
* **ABC Analysis Insight:** Unlike typical business data (which follows the 80/20 Pareto rule), the PubChem mass distribution is highly uniform. It requires classifying ~69% of the compounds into "Class A" to account for 80% of the total dataset mass.
* **Structural Variance:** Analysis revealed a moderate positive correlation (0.41) between mass and lipophilicity. Furthermore, an increase in Hydrogen Bond Acceptors (HBA) drastically increases not only the median molecular weight but also the structural variance (dispersion) of the compounds.

## 🛠️ Tech Stack
* **Language:** Python 3
* **Data Manipulation:** Pandas, NumPy, SciPy (Statistics)
* **Data Visualization:** Matplotlib, Seaborn
* **Domain Library:** RDKit (Cheminformatics)

## 📁 Repository Structure
* `pubchem_exploratory_data_analysis.ipynb`: The main Jupyter/Colab notebook containing the fully commented code, visualizations, and logic.
* *(Note: The raw .sdf files and the final 2M-row .csv are excluded from this repository due to GitHub file size limits, but the code to generate them is fully reproducible).*

---
*Created by Yaroslav Matvienko as part of a Data Analytics portfolio.*
