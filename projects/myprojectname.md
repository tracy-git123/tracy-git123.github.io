---
layout: project
type: project
image: img/tumblr_a5cfd650e8226c6606a19837ceed15f7_748aa473_500.jpg
title: "Public Housing Demand in Johannesburg"
date: 2019
published: true
labels:
  - Python
  - Exploratory Data Analysis (EDA)
summary: "This was an exploratory data analysis of a public housing applicant database."
---

<div class="text-center p-4">
  <img width="200px" src="../img/micromouse/micromouse-robot.png" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-robot-2.jpg" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-circuit.png" class="img-thumbnail" >
</div>

Millions of people move to Johannesburg every year in search of opportunities, yet the housing market is not able to keep up with demand.
The government's Department of Human Settlements fund housing programmes in all municpalities such as Johannesburg in order to provide housing to citizen.
This project explores the housing applicant data for citizens in the City of Johannesburg which stands at approximately 450,000 people.

Here is a summary of rows which have data in each column and as we can see several columns have data gaps where no values were entered:

```cpp
newdf.count()


ProvinceID            455791
Municipality          455791
TownName              455791
Region                455791
Area                  455791
QuestionaireID        455791
Registration Date     455791
Year                  455791
Month                 455791
Day                   455791
StreetName            454786
HouseNo               455498
WardNo                 25097
HomeTelNo             216429
WorkTelNo               1843
CellNo                290476
Relationship          455791
Age Main Member       455388
Gender Main Member    455786
Spouse Age             36302
Spouse GenderID        36305
MonthlyIncome         455717
HSS Status            455791
DwellingType          455788
EnergySource          455788
Sanitation            455788
Water                 455788
Disability             73683
dtype: int64
```

You can learn more at the [UH Micromouse News Announcement](https://manoa.hawaii.edu/news/article.php?aId=2857).
