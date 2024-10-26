# AUPowerBIWorkshop

## Creating Report in Fabric
- Create new workspace
- Create new data lake
- Create new data flow Gen2
  - import data table
  - clean and prep data (for details, see below)
  - connect to data lake (add destinations)
- Go to data lake "Reporting" tab, create new report
- Make visualizations
- Set-up refresh

## Data Cleaning

Your goal is to append the two data tables row-wise, and remove duplicates.
We will create column "Key" = "{CompanyName}|{LayoffDate}" to remove duplicates.
The two tables must have the same set of column names.

**layoff1**
- Transform column types to percentage
- Trim the text column
- Add a new column called "stage_ranking"
  `if Text.Contains([stage], "IPO") then 90 else if Text.Contains([stage], "Private") then 80 else if Text.Contains([stage], "Subsidiary") then 20 else if Text.Contains([stage], "Acquired") then 30 else if Text.Contains([stage], "Merged") then 30 else if [stage] = "Seed" then 40 else if [stage] = "Series A" then 50 else if [stage] = "Series B" then 50 else if [stage] = "Series C" then 50 else if Text.StartsWith([stage], "Series") then 60 else 0`
- Add a new column called "key"
`Text.Combine({[company], "|", Date.ToText([date], "yyyy"),Date.ToText([date], "MM"), Date.ToText([date], "dd")})`
- Set column names:
- [company, city, industry, layoff_count, layoff_percentage, date, stage, country, funds_raised, stage_ranking, key]

**layoff2**
- Do it yourself
- Notes
  - Need to rename most columns
  - Remove unnecessary columns
  - When adding key and stage_ranking columns, make sure your command is consistent with the column names

**merging**
- Append as new
- Remove duplicates
- Replace null with 0 for `percentage_laid_off`
