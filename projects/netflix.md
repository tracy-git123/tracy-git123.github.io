---
layout: project
type: project
image: img/TV shows and movies.png
title: "Netflix Wrapped"
date: 2023
draft: true
#published: true
labels:
  - Data visualistion
  - Data story
  - Python
  - Netflix
summary: "Riding on the wave Spotify Wrapped, I was inspired to create 5 data visualisations which summarise my Netflix watching habits for 2023."
---
If you are unfamiliar with [Spotify Wrapped](https://en.wikipedia.org/wiki/Spotify_Wrapped) it's an end-of-year review of listening habits on the platform. Despite having a wealth of data, Netflix does not give users any personalised insights into their watching habits so I decided to take on the project for myself and call it Netflix Wrapped.

Netflix Wrapped was written using Python and Matplotlib. Within a week I was able to download my usage data, clean the data and create 5 data visualisations. Through this project I gained experience with creating:
* radial graphs
* dumb bell graphs
* radar graphs
* maps

Below I'll take you through what I did to prepare the data and what findings emerged. See my Netflix Wrapped essay for an extended discussion on what transpired during in this project.

# Genres watched
<img width="400px" 
     class="rounded float-start pe-4" 
     src="../img/netflix_genres.png">

## Data prep
I consulted IMDB, pulled their 27 genre categories and created 2 new fields for genre category: a primary category and, in some cases, a secondary category for each title in my list. (One title represents a unique TV show or Movie title)

## Findings
My top 5 favourite genres were Comedy, Documentary, Drama, Game-shows, with Thrillers, Crime and Animation tied for fifth place. 


# Bingeing habits 🍿

<img width="600px" 
     class="rounded float-start pe-3" 
     src="../img/netflix_radial_plot.png">

## Data prep
Here I had to ensure I had clean and well-formatted data in the ‘date_watched’ field of my dataframe. Additionally it was important to have a ‘title’ and an ‘episode_name’ field to differentiate and enable me to count unique show or movie titles and unique episodes which may be part of a series. In hindsight I could have included additional field for ‘season’ for cases where I watched multiple seasons of the same title, however the naming convention around this is not always consistent for example:

|Title                                                                                    |
|------------------------------------------------------------------------------------|
| Adventure Time: Season 4: In Your Footsteps / Hug Wolf                             | {Title} {Subtitle} {Season} {Episode name}
| BEEF: Season 1: Figures of Light                                                   | (Title) [Season] {Episode name}
| Astronomy Club: The Sketch Show: Season 1: Lamp Room                               | Title - Subtitle - Season - Episode name
|------------------------------------------------------------------------------------|
| Larry Charles' Dangerous World of Comedy: Season 1: Part 3: Race                   |
| Kaleidoscope: Limited Series: Red (The Morning After the Heist)                    |{Title}/{Series type}/{Episode name}
| Stateless: Limited Series: The Seventh Circle                                      |{Title / Series type / Episode name
| Big Vape: The Rise and Fall of Juul: Limited Series: Overnight Billionaires        |
|------------------------------------------------------------------------------------|

|                                                                                    |
| Top Boy: Summerhouse: Series 2: Episode 1                                          |
| Top Boy: Season 3: If We Are Not Monsters                                          |
|                                                                                    |
| Master of None: Season 3: Moments in Love, Chapter 2                               |
|                                                                                    |
| RuPaul's Drag Race: Season 9: She Done Already Done Brought It On                  |
| RuPaul’s Drag Race: All Stars: Season 6: Rumerican Horror Story: Coven Girls       |
|                                                                                    |
| Babies: Part 2: Movement                                                           |
| Avatar: The Last Airbender: Book 1: The Warriors of Kyoshi                         |
| jeen-yuhs: A Kanye Trilogy: act i: VISION                                          |
|                                                                                    |
| Bad Sport: Volume 1: Fallen Idol                                                   |
| Patriot Act with Hasan Minhaj: Volume 4: Why Your Public Transportation Sucks      |
| Dear White People: Volume 1: Chapter I                                             |
|                                                                                    |
| BoJack Horseman: Season 1: BoJack Horseman: The BoJack Horseman Story, Chapter One |


