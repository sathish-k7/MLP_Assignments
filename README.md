# MLP Assignments

This repository contains Machine Learning and Data Analysis assignments with comprehensive dataset analysis and preprocessing.

## Project Structure

### Week 1: Dataset Analysis & Querying
- **Dataset**: `week1/Week1_GA_dataset.csv` (10,000 × 12 real estate data)
- **Notebooks**:
  - `Week1.1_Dataset_Analysis.ipynb`: Data cleaning, missing value analysis, row/column queries
  - `Week1.2_Dataset_Analysis.ipynb`: Indexing, slicing, conditional filtering operations

**Key Results Week 1.1**:
- Unknown values: 5,548 total (1,823 literal "?" + 3,725 original NaN)
- Missing value analysis and data cleaning operations
- Row filtering based on missing value thresholds

**Key Results Week 1.2**:
- Even/odd row and column extraction
- Year-based filtering and conditional queries
- August property counts and locality-based price analysis

### Week 2: Machine Learning Preprocessing
- **Dataset**: `week2/GA_2_dataset.csv` (10,000 × 13 gaming engagement data)
- **Notebook**: `Week2_Dataset_Analysis.ipynb`

**Preprocessing Pipeline**:
1. **Data Type Analysis**: Identified object columns (Gender, Location, GameGenre, GameDifficulty, EngagementLevel)
2. **Missing Value Handling**: 3,337 total null values across Age, Location, InGamePurchases, GameDifficulty
3. **Imputation Strategy**:
   - Age: Mean imputation from training data
   - Location: NaN → "Other"
   - GameDifficulty: Mode imputation
   - InGamePurchases: NaN → 0
4. **Feature Engineering**:
   - Ordinal encoding: GameDifficulty (Easy=0, Medium=1, Hard=2)
   - One-hot encoding: Gender, Location, GameGenre (drop_first=True)
   - StandardScaler: All numerical features
5. **Train-Test Split**: 80-20 split, random_state=42

**Final Answers**:
- Q1: Object columns: Gender, Location, GameGenre (from specified list)
- Q2: Males from Europe with purchases: 299
- Q3: Under-18 players with >10h playtime: 453
- Q4: Total null values: 3,337
- Q5: Least frequent target class: High (1,996 samples)
- Q6: Sum of transformed Age (test): 16.50 (standardized) | 63,585.24 (imputed raw)
- Q7: Sum of first 5 transformed rows: -7.17 (full scaling) | 6.84 (numeric-only scaling)

## Technical Implementation

**Dependencies**: pandas, numpy, scikit-learn  
**Preprocessing Approach**: Complete-case statistics → Imputation → Encoding → Scaling  
**Validation**: Multiple verification cells ensure reproducibility and cross-check different interpretations

## Methodology Notes

The notebooks include comprehensive verification sections that explore different interpretations of "transformed" data:
- Raw vs. standardized feature values
- Numeric-only vs. full-feature scaling approaches
- Complete-case vs. all-data statistics for imputation

All results are reproducible with the provided random seeds and preprocessing steps.