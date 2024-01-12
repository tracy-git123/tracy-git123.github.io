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

Netflix Wrapped was written using Python and Matplotlib. Within a week I was able to download my usage data, clean the data and create 5 data visualisations. Through this project, I gained experience with creating:
* radial graphs
* dumb bell graphs
* radar graphs
* maps

Below I'll take you through what I did to prepare the data and what findings emerged. See my Netflix Wrapped essay for an extended discussion on what transpired during this project.

# Genres watched
<img width="400px" 
     class="rounded float-start pe-4" 
     src="../img/netflix_genres.png">

Here I pulled the 27 genre categories used on the IMDB and categorised every title on my list into a primary genre and secondary genre where necessary. One title represents a unique TV show or Movie title.

My top 5 favourite genres were Comedy, Documentary, Drama, Game-shows, with Thrillers, Crime and Animation tied for fifth place. 


# Bingeing-watching 🍿

<img width="400px" 
     class="rounded float-start pe-4" 
     src="../img/netflix_radial_plot.png">

<img width="400px" 
     class="rounded float-start pe-4" 
     src="../img/netflix_fastest.png">

It’s well-known that many video streaming platforms like Netflix and Youtube are built to keep you watching so you could say binge-watching is a key marker of success for these platforms. And let’s just say the house always wins.

## Key Stats
- In 2023 I watched 450 unique titles. 
- 67 of these were once-off shows or movies and 383 were episodes in a series.
- Fastest watch time: 8 episodes in 1 day 🏁 

Binge-watching peaked in March for me, when I watched 3 different game shows from start to finish. In September my viewing peaked again with 55 titles watched, which coincided with the much-anticipated drop of the final season of _Sex Education_. When I looked deeper into why I watched 20 episodes of _Sex Education_ in September it was clear that after watching the 8 episodes of the final season I had a period of withdrawal about the show being over and proceeded to watch 12 more episodes from previous seasons. In my essay, I further discuss the pros and cons of the binge-watching strategy employed by Netflix.

​​# Places I went with Netflix Airlines  ✈️ 

<img width="400px" 
     class="rounded float-start pe-4" 
     src="../img/netflix_map (1).png">
     
I have always considered my taste in entertainment to be very diverse and global but I wondered if the data would match up.
For this visualization I categorized my viewing history manually by recalling the language and location of each title. 

Again I briefly considered using the IMDB API but abandoned that idea because only a handful of shows are from outside Hollywood so there was minimal classification to do.

For this visualisation the map, labels and dots were the easy part. I spent the longest time trying to get the lines to be drawn in a neat way. I eventually settled on writing code for the lines to be drawn between points which were in a similar latitude or longitude range but upon closer inspection the locations are just connected in the descending order as they appear in the data. Sometimes complex code is road to nowhere.

Findings

I think TV and movies are great ways to explore new perspectives and places and venture out of your comfort zone with relative ease and at a low lost. I’ve truly enjoyed going off the beaten path of Hollywood and being immersed in strange new contexts and storylines. 

It’s awesome to see the incredible amount of non-American content Netflix actually has available. I have managed to watch several Brazilian, South African and Kenyan titles but most bizarrely 2023 has been the year of Austrailian content for me. Although unremarkably all English content, there have been strong contenders like the funny Gen-X show Why Are You Like This? or the dry-humor from Fisk which might make you nostalgic for The Office - George has cemented his own place as an iconic receptionist next to Pam. (It’s also so strange to find a show where netball features so prominently in the script. Netball had a glo-up!) An honourable mention must also go to the migrant-drama Stateless for excellent acting and gripping story-telling. 

It also seems that any foreign-language content I watch seems to overlap with the many languages I am juggling in Duolingo. I’m always so impressed by the movies that come out of Kenya for how gritty and real they are. Veve in particular had really tight and compelling story paired with some excellent acting performances - who knew Savara from Sauti Sol could act like that and seamless weave singing into his character, genius.  Although I was almost completely reliant on the subtitles I still enjoyed the French comedy Nothing to Hide (also can someone explain to me if all foreign-language films have an English title? Because that would mean we are totally judging a book by it’s cover.)

The one Brazilian show I watched really opened my eyes to a culture so different to mine - one where the host does unnecessary stunts like climbing a ladder in 10 inch heels and where people have really tenuous relationships with the mother-in-laws. It was truly an emotional roller-coaster.

Remarks: 
Am I obsessed with Australia? 🦘

My taste is somewhat global but I watched 6 shows this year from Australia this year, mostly comedy. 😂

Faves:
✴️Fisk
✴️
✴️The Mole 

(Yes I left out all the content I watched from America because obvs most content comes from there so I wouldn’t bore you with that detail.)


