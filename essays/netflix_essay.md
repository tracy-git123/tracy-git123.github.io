---
layout: essay
type: essay
title: "Looking into my Netflix data"
# All dates must be YYYY-MM-DD format!
date: 2023-12-16
published: false
labels:
  - Data Analysis
  - Film & TV
  - Entertainment
---

## Genres watched

**Data prep**

Step 1: Organise the data according to genre.

My initial plan was to use an official Netflix API to pull the genre values for each title in my watch history but it turns out	there is no API because apparently, Netflix put out a statement saying that “To better focus our efforts and to align them with the needs of our global member base,” the company would shut down its public API. 

Reelgood could be used as an alternative but it was too costly to pay for. So instead I consulted IMDB and copied their genre categories. Finally, I manually assigned a primary category and, in some cases, a secondary category for each title in my list because lots of content does not fit neatly into one genre. As an aside, there might be some room for debate with IMDB about what differentiates a Thriller from a Mystery but I digress. I also briefly considered using the IMDB API but abandoned that idea because I thought it would slow me down and I was done with the manual categorisation of 121 titles in about 30 minutes.

**Findings**

> My top 5 favourite genres were:
> - Comedy
> -  Documentary
> -  Drama
> -  Game-shows
> -  Thrillers, Crime and Animation tied for fifth place. 

I had many internal debates about the categories and where some shows should go. For instance, is _Orange Is The New Black_ a crime, comedy or drama show? Is _Black Mirror_ perhaps a sci-fi, dark-comedy show? To what extent was _The Crown_ a historical documentary or a high-profile family drama? And to all these question my answer is yes. It all applies. Much of my favourite content is layered and straddles multiple genres. I loved a good dramedy (drama + comedy) like _Pain Hustlers_ or _BEEF_ and was equally delighted by the unique comedy + mystery combo in movies like _They Cloned Tyrone_ and _Shimmer Lake_. 

With Documentaries being my 2nd favourite genre I appreciate Netflix’s ability to source and deliver compelling serialised documentaries. I was utterly fascinated by the depth and story-telling in _Free Money_, _MH370: The Plane That Disappeared_, _Beckham_, _Big Vape_ and _Senzo: Murder of a Soccer Star_ (desperately hoping season 2 of _Senzo_ is on the way!).

## Bingeing habits 🍿

**Data prep**

Step 2: Organise the data according to date started and date finished

Here I had to ensure I had clean and well-formatted data in the ‘date_watched’ field of my dataframe. Additionally it was important to have a ‘title’ and an ‘episode_name’ field to differentiate and enable me to count unique show or movie titles and unique episodes which may be part of a series. 

I briefly considered creating an additional field for ‘season’ to enable me to drill on the ways I watched seasons of the same title, however the naming convention around seasons is not always consistent for example:

### the traditional-ish bunch
`title` ~ `season number` ~ `episode name`
- BEEF: Season 1: Figures of Light
- Top Boy: Season 3: If We Are Not Monsters
- Adventure Time: Season 4: In Your Footsteps / Hug Wolf
- Master of None: Season 3: Moments in Love, Chapter 2
- RuPaul's Drag Race: Season 9: She Done Already Done Brought It On

`title` ~ `subtitle` ~ `season number` ~ `episode name`
- Top Boy: Summerhouse: Series 2: Episode 1
- Astronomy Club: The Sketch Show: Season 1: Lamp Room
- RuPaul’s Drag Race: All Stars: Season 6: Rumerican Horror Story: Coven Girls

`title` ~ `subtitle` ~ `season number` ~ `part` ~ `episode name`
- Larry Charles' Dangerous World of Comedy: Season 1: Part 3: Race
  
### the limited series bunch
`title` ~ `series type` ~ `episode name`
- Kaleidoscope: Limited Series: Red (The Morning After the Heist)
- Stateless: Limited Series: The Seventh Circle

`title` ~ `subtitle` ~ `series type` ~ `episode name`
- Big Vape: The Rise and Fall of Juul: Limited Series: Overnight Billionaires

### the bunch which refused to use the word 'season'
`title` ~ `part` ~ `episode name`
- Babies: Part 2: Movement
- Avatar: The Last Airbender: Book 1: The Warriors of Kyoshi
- jeen-yuhs: A Kanye Trilogy: act i: VISION

`title` ~ `volume` ~ `episode name` 
- Bad Sport: Volume 1: Fallen Idol
- Patriot Act with Hasan Minhaj: Volume 4: Why Your Public Transportation Sucks
- Dear White People: Volume 1: Chapter I

`and then there's bojack`
- BoJack Horseman: Season 1: BoJack Horseman: The BoJack Horseman Story, Chapter One


**Findings**

It’s well-known that many video streaming platforms like Netflix and YouTube are built to keep you watching so you could say binge-watching is a key marker of success for these platforms. Let’s just say the house always wins and the cliff-hangers employed worked on me. Aside from Netflix actively trying to keep me locked in by any means necessary, my curiosity and love for good story-telling also contribute to my binge-sessions.

In 2023 I watched 450 unique titles. 67 of these were once-off shows or movies and 383 were episodes in a series. The data revealed I am a loyalist for the most part, and if I find a show I like, I watch it all before moving on. In March specifically, I watched an entire season of 3 different game shows. It makes sense that bingeing and game shows are a powerful combo as viewers look forward to seeing the next challenge for contestants and the drama of who is safe, who gets eliminated, and who eventually wins the prize. The cause-and-effect nature of these shows is exciting and is a built-in cliffhanger, because where else in our lives can we observe such immediate results? I recall the game shows _The Mole_ and _Is It Cake?_ used this strategy brazenly by always introducing the next episode’s challenge, at the end of the current episode, to the point where each  series started to feel like one really long take. It was like drowning in an uninterrupted stream of content with no moment to pause.

In September my viewing peaked again with 55 titles watched, which coincided with the much-anticipated drop of the final seasons of _Top Boy_ and _Sex Education_. Instead of drowning, I felt like I was savouring these shows. I sometimes even had the self-restraint to only watch two episodes a day 😇.

As a viewer it is both exciting and overwhelming when an entire season of _Top Boy, Sex Education_ or _The Crown_ is dropped in one go. These shows often have really long production and post-production periods which only add to the anticipation. Although it may feel like winning the lottery when you stumble upon a whole new season of your favourite show I feel there are also some down-sides to Netflix’s binge-release strategy:

- _Walking on egg-shells_: We can’t talk freely about the dramatic mid-series plot twist or scandalous finale because we don't know where our friends may be within the series and we don’t want to risk giving or receiving a spoiler. As a result, we keep a vow of silence for however many weeks (or days) it takes everyone to watch the show. On the one hand, you may be bursting at the seams to talk to someone but on the other hand, you may have to dodge spoilers from all directions while feeling pressured by some invisible force to binge ASAP to avoid being left behind.

- _The mammoth task of unpacking_: Now that we’ve all watched 10 hours of content, how do we recall AND unpack how _all_ the events delighted and surprised us? It’s nearly impossible and so the conversation goes something like this: have a 10-minute surface-level chat, where episodes get blurred together, we touch on some general plot points and then briefly discuss the ending. Tragic. This really doen';t do justice to some excellent productions out there. It feels like gone are the beautiful days of _Insecure_ where we all watched together and had all week to unpack and kiki over the latest 30-minute episode before the next installment. The Condola jokes or iconic ad-libs from Kelly that percolated on social media for that week were a testament to the delightful things that can happen when you give an episode some time to breathe on a weekly release schedule. 

## Places I went with Netflix Airlines ✈️

**Data Prep**

Step 3: Organise data according to geographic origin

For this visualisation I categorized my viewing history manually by recalling the language and location of each title. Again I briefly considered using the IMDB API here but abandoned that idea because only a handful of shows are from outside Hollywood so there was minimal classification to do.

For this visualisation the map, labels, and dots were the easy part. I spent the longest time trying to get the lines to be drawn neatly. I eventually settled on writing code for the lines to be drawn between points that were in a similar latitude or longitude range but upon closer inspection, the locations are just connected in the descending order as they appear in the data. Sometimes trying to write sophisticated code is a road to nowhere.

**Findings**

I think TV and movies are great ways to explore new perspectives and places and venture out of your comfort zone with relative ease and at a low cost. I’ve truly enjoyed going off the beaten path of Hollywood and being immersed in strange new contexts and storylines. 

It’s awesome to see the incredible amount of non-American content Netflix has available. I have managed to watch several Brazilian, South African and Kenyan titles but most bizarrely 2023 has been the year of Australian content for me. I particularly enjoyed the funny Gen-X show _Why Are You Like This?_ and the dry humor from _Fisk_ which might make you nostalgic for _The Office_ (IMO George has cemented his place as an iconic receptionist next to Pam.) An honourable mention must also go to the migrant-drama _Stateless_ for excellent acting and gripping story-telling. 

Looking at the data through a language lens, most of what I watched was unremarkably in English. What I did notice is that it seems any foreign-language content I watch seems to overlap with the languages I am juggling in Duolingo. I’m always so impressed by the movies that come out of Kenya for how gritty and real they are. _Veve_ in particular had a tight and compelling story paired with some excellent acting performances - who knew Savara from _Sauti Sol_ could act like that and seamlessly weave singing into his character, genius.  Although I was almost completely reliant on the subtitles I still enjoyed the French comedy _Nothing to Hide_ (also can someone explain to me if all foreign-language films have an English title? Because that would mean we are most certainly judging a book by its cover, no?)

