# AUPowerBIWorkshop

## Notes
During data manipulation, syntax for creating "StageRanking": 
each if Text.Contains([stage], "IPO") then 90 else if Text.Contains([stage], "Private") then 80 else if Text.Contains([stage], "Subsidiary") then 20 else if Text.Contains([stage], "Acquired") then 30 else if Text.Contains([stage], "Merged") then 30 else if [stage] = "Seed" then 40 else if [stage] = "Series A" then 50 else if [stage] = "Series B" then 50 else if [stage] = "Series C" then 50 else if Text.StartsWith([stage], "Series") then 60 else 0)
