# Take-Home Assignment: Cucumber Weight Regression Pipeline

## Objective
Build a clear, reproducible Python workflow to predict `cucumber_weight` from genotype marker and environmental data. Please do not spend more than 4-5 hours on this. Focus more on clean professional code, documentation, reproducibility and less on model performance. 

We are evaluating your ability to:
1. Explore and understand a high-dimensional dataset.
2. Prepare data for modeling in a robust and transparent way.
3. Engineer practical features that improve signal quality.
4. Report model performance clearly and reproducibly.

## Dataset
The synthetic dataset contains:
- 5000 cucumber observations (rows)
- 1000 SNP marker columns per plant (values like `AA`, `AG`, `GG`)
- Environmental variables measured across 5 time points each:
  - `temp_1..temp_5`
  - `humidity_1..humidity_5`
  - `co2_ppm_1..co2_ppm_5`
  - `light_hours_1..light_hours_5`
  - `soil_ec_1..soil_ec_5`
  - `irrigation_ml_1..irrigation_ml_5`
- Target column: `cucumber_weight`


## Tasks
### NOTE: The main deliverable is the final working code. Intermediate steps don't have to be delivered.


### 1) Explore the dataset
Perform brief EDA and summarize findings:
- Data shape and column groups
- Missingness and invalid values (if any)
- Distribution of target (`cucumber_weight`)
- Basic feature relationships/correlations (especially environmental summaries)

### 2) Preprocess data
Implement a reproducible preprocessing pipeline:
- Handle missing values with explicit strategy
- Encode SNP values (e.g., additive encoding or one-hot)
- Handle numeric scaling if needed
- Keep train/validation split leakage-free

### 3) Feature engineering
Create at least a few useful derived features, such as:
- Genotype completeness (% non-missing SNPs)
- Heterozygosity rate (% `AG` markers)
- Environmental aggregates (mean/min/max/std across time points)
- Optional interaction features if justified

### 4) Build models and validate
Train simple model(s) and report model performance on validation/test split. 


## Deliverables
Submit:
1. Source code (`.py` files) 
2. `README.md` with setup and run instructions 
3. `requirements.txt` (or environment file) 
4. Output artifacts: 
   - `metrics.json` (or CSV table with model metrics) 
   - `feature_summary.csv` (or equivalent engineered dataset sample) 
5. Saved models
6. A description or overview flowchart of how you would create a pipeline around this and put it on production in cloud.
7. Please create git repository on gitlab/github and share the link with us


## Technical Expectations
- Keep code modular and readable
- Avoid hardcoded absolute paths
- Ensure reproducibility
- **Data handling quality:** preprocessing and missing/invalid handling.
- **Modeling & evaluation:** Again, please focus on a working code that is close to production ready. It's fine if your model performance is not great but please report metrics.  
- **Code quality & hygiene:** structure, naming, clarity, reproducibility.