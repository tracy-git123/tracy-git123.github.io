---
layout: project
type: project
image: img/TV shows and movies.png
title: "Netflix Wrapped"
date: 2023
published: true
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

Below I'll take you through what I did to prepare the data and what findings emerged

# Genres watched

<img class="img-fluid" src="../img/netflix_genres.png">

## Data prep
My initial plan was to use an official Netflix API to pull the genre values for each title in my watch history but it turns out	there is no API because apparently in a letter to developers, Netflix explained that “To better focus our efforts and to align them with the needs of our global member base,” the company would shut down its public API. Reelgood could have stood in this gap but it was too costly to pay for. So instead I consulted IMDB, pulled the genre categories used in the filter feature and create 2 new fields for genre category. Finally I manually assigned a primary category and, in some cases, a secondary category for each title in my list.

As an aside there might be some room for debate with IMDB about what differentiates a Thriller from a Mystery but I digress. I also briefly considered using the IMDB API but abandoned that idea because it thought it would slow me down and I was done with the manual categorisation of 121 titles in about 30 minutes.

## Findings
My top 5 favourite genres were Comedy, Documentary, Drama, Game-shows, with Thrillers, Crime and Animation tied for fifth place. 

I had many internal debates the about the categories and where some shows should go. For instance is Orange Is The New Black a crime, comedy, drama show? Is Black Mirror perhaps a sci-fi, dark-comedy show? To what extent was The Crown a historical documentary or a high-profile family-drama? And to all these question my answer is just, yes. It all applies. Much of my favourite content is layered and straddles multiple genres. I loved a good dramedy (drama + comedy) like Pain Hustlers or BEEF and was equally delighted by the comedy + mystery combo in movies like They Cloned Tyrone and Shimmer Lake. 

With Documentaries being my 2nd favourite genre I really appreciate Netflix’s ability source and deliver compelling serialised documentaries. I utterly fascinated by the depth and story-telling in Free Money, MH370: The Plane That Disappeared, Beckham, Big Vape and Senzo: Murder of a Soccer Star (desperately hoping season 2 is on the way)


# Bingeing habits 🍿

<img class="img-fluid" src="../img/netflix_radial_plot.png">

## Data prep
Here I had to ensure I had clean and well-formatted data in the ‘date_watched’ field of my dataframe. Additionally it was important to have a ‘title’ and an ‘episode_name’ field to differentiate and enable me to count unique show or movie titles and unique episodes which may be part of a series. In hindsight I could have included additional field for ‘season’ for cases where I watched multiple seasons of the same title, however the naming convention around this is not always consistent for example:

Kaleidoscope: Limited Series: Red (The Morning After the Heist)
Stateless: Limited Series: The Seventh Circle
Big Vape: The Rise and Fall of Juul: Limited Series: Overnight Billionaires
Adventure Time: Season 4: In Your Footsteps / Hug Wolf

BEEF: Season 1: Figures of Light
Astronomy Club: The Sketch Show: Season 1: Lamp Room

Larry Charles' Dangerous World of Comedy: Season 1: Part 3: Race

Top Boy: Summerhouse: Series 2: Episode 1
Top Boy: Season 3: If We Are Not Monsters

Master of None: Season 3: Moments in Love, Chapter 2

RuPaul's Drag Race: Season 9: She Done Already Done Brought It On
RuPaul’s Drag Race: All Stars: Season 6: Rumerican Horror Story: Coven Girls

Babies: Part 2: Movement
Avatar: The Last Airbender: Book 1: The Warriors of Kyoshi
jeen-yuhs: A Kanye Trilogy: act i: VISION

Bad Sport: Volume 1: Fallen Idol
Patriot Act with Hasan Minhaj: Volume 4: Why Your Public Transportation Sucks
Dear White People: Volume 1: Chapter I

BoJack Horseman: Season 1: BoJack Horseman: The BoJack Horseman Story, Chapter One


