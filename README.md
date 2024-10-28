# AUPowerBIWorkshop

## Creating Report in Fabric
- Download data sets from this repo to your local laptop (source: https://www.kaggle.com/datasets/swaptr/layoffs-2022)
- Create new workspace
- Create new data lake
- Create new data flow Gen2
  - import data tables
  - clean and prep data - I did this for you, mostly - see next section. 
  - connect to data lake
- Go to data lake "Reporting" tab, create new report
- Make visualizations
    - map chart
    - stacked bar + line chart
    - adding filter
    - tooltip
    - changing color
- Set-up refresh in data flow

## Data Prep Details
**renaming tables**
Load Layoff1_cleaned, and rename it to "layoff1"
Load Layoff2_cleaned, and rename it to "layoff2"

**creating new columns**
- Add a new column called "Key" : 
  
`Text.Combine({[Company], "|", Date.ToText([Date], "yyyy"),Date.ToText([Date], "MM"), Date.ToText([Date], "dd")})`

**merging**
- Append as new
- Remove duplicates using the key column


