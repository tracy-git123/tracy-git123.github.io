---
layout: project
type: project
image: img/micromouse/micromouse-square.jpg
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

Here is some code that illustrates how we read values from the line sensors:

```cpp
byte ADCRead(byte ch)
{
    word value;
    ADC1SC1 = ch;
    while (ADC1SC1_COCO != 1)
    {   // wait until ADC conversion is completed   
    }
    return ADC1RL;  // lower 8-bit value out of 10-bit data from the ADC
}
```

You can learn more at the [UH Micromouse News Announcement](https://manoa.hawaii.edu/news/article.php?aId=2857).
