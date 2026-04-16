**Cucumber weight prediction pipeline**

General overview


**Set up and run instructions**

Project Structure
- main.py: point of entry to pipeline
- requirements.txt
- config.yaml: custom setup for pipeline configuration and specifications 
- README_cucumber_yield_prediction_assignment.md
- README_setup_and_run_instructions.md
- data
  - raw
    - cucumber_yield_raw_genotypes.csv
- src
  - eda.py: Contains plotting logic for initial EDA and final model evaluation
  - processor.py: Handles quality checks, missing data, snps recoding and so on
  - feature_engineering.py: Engineer features and prepare data for modeling
  - modeling.py: Contains the modeling logic for using GPR as proxy for GBLUP. Builds and saves model
  - predict.py: Loads existing model to predict new individuals

