---
layout: project
type: project
image: img/368-3681800_netflix-png-transparent-image-netflix-png.png
title: "Netflix Wrapped"
date: 2023
published: true
labels:
  - Data visualistion
  - Data story
  - Python
  - Netflix
summary: "Similar to Spotify Wrapped, I created data visualisations of my Netflix watch history data for 2023."
---

<div class="text-center p-4">
  <img width="200px" src="../img/micromouse/micromouse-robot.png" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-robot-2.jpg" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-circuit.png" class="img-thumbnail" >
</div>

Visualisations created include
Genres
Watch speed for series
Highest viewing months
Conutries where content originates from

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
