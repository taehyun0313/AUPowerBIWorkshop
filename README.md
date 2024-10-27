# AUPowerBIWorkshop

## Creating Report in Fabric
- Download data sets from this repo to your local laptop (source: https://www.kaggle.com/datasets/swaptr/layoffs-2022)
- Create new workspace
- Create new data lake
- Create new data flow Gen2
  - import data table
    - rename layoff_data to layoffs2
  - clean and prep data (for details, see below)
  - connect to data lake (add destinations)
- Go to data lake "Reporting" tab, create new report
- Make visualizations
- Set-up refresh in data flow

## Data Cleaning

**merging**
- Append as new
- Remove duplicates
