# Augustus LaFortune

## Final Project Ideas:
**1. Library occupancy**
- I already [have this data](https://docs.google.com/spreadsheets/d/1W0Ir9_vkeeeAdqxTlNZ9y3OYto_xcfIPKoz45YwRwQ4/edit?usp=sharing) recorded at 10 minute intervals since 5/18/2025. I can combine this data with other things such as a list of courses (when they start and end), the weather, the college calendar, and the events calendar.
- <ins>Questions to answer</ins>: Does weather affect library occupancy? Does the occupancy level change throughout the semester (due to increased workload as the semester progresses)?

**2. Word analysis of TV show**
- Inspect script of a TV show. If inspecting more than one script, then compare them to each-other in terms of words used, words per line, or sentiment.
- I have found a full transcript of both [Cheers](https://subslikescript.com/series/Cheers-83399) and [The Office (U.S.)](https://bradlindblad.github.io/schrute/). The one for The Office is much more detailed, including the speaking character's name, the names of the writers of the episode, the IMDB rating of the episode, the air-date, etc. It also is already organized into a single file. The one for Cheers is much more simple, only plainly listing the lines in the order they were spoken and in what episode. However, I could combine this data with IMDB data of the episode.
- <ins>Questions to answer</ins>: Does the sentiment of the dialogue in an episode correlate to the IMDB rating for the episode? (Do different rating websites exhibit the same behavior, or are some more influenced by sentiment than others?) Does the frequency of a name being used in an episode correlate to the ratings for the episode? 

**3. Whitman Campus trees**
- I know that there is a dataset of (almost) all trees on the Whitman campus that, for each tree, includes its species name, family name, common name, leaf fall, and geographic coordinates. (I know that there is such a dataset because I have found an [unfinished GitHub project](https://github.com/Luckykhoza1/WhitmanTrees-Demo) that uses the dataset of over 6,000 trees.)
- I can combine this dataset with things like data of campus building footprints (easily found in OpenStreetMap).
- <ins>Questions to answer</ins>: Does the type of tree correlate to its distance from the closest building? Does the type of tree correlate to its location on campus?

## Week 10 Update
- I have settled on doing word analysis of a TV show as my topic for the final project.
- I will be doing this project by myself.
- I am going to look at things like how often two words appear in the same line, the frequency of names throughout the series, etc.
- I am either going to use a transcript for the TV show Cheers, or The Office. In preparation for this project I wrote a webcrawler using jsoup for Java to get all of the transcripts for Cheers from a TV show transcripts website. The program organized all of the lines into a single .csv file that, for each line, includes the season number, episode number, and episode title. However, some of the episodes have single letters swapped for others (for example, in some episode the letter "I" is replaced by "l"). 
