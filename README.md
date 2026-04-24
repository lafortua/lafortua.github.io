# Augustus LaFortune
(Last edited on 4-24-2026)

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
- I am either going to use a transcript for the TV show Cheers, or The Office.
    In preparation for this project I wrote a webcrawler using jsoup for Java to get all of the transcripts for Cheers from a TV show transcripts website. The program organized all of the lines into a single .csv file that, for each line, includes the season number, episode number, and episode title. I could probably combine this dataset with another dataset such as the IMDB rating for each episode. However, some of the episodes have single letters swapped for others (for example, in some episode the letter "I" is replaced by "l"). I think that this is possible to fix in some cases and will not be very consequential in other cases.
    Alternatively, I could use an existing, clean, and well organized dataset of the lines from The Office. For each line, this dataset includes everything my Cheers dataset does, in addition to the writer of the episode, the director of the episode, the character who speaks the line, a version of the line that includes acting direction (such as "walk away"), the IMDB rating of the episode, the number of ratings for the episode, and the date that the episode aired. However, I worry that this will not be as interesting of a dataset to work with because [it has already been analysed multiple times before](https://www.jennadallen.com/post/text-analytics-every-line-from-the-office/).
- Three questions I want to explore:
    Which character's name appears in the same line as the word "beer" the most? (I suspect it would be the character named Norm, but perhaps it is one of the waiters or bartenders).
    Which character's name appears the most in lines that end with "!". What about "?".
    Does the sentiment of the lines change throughout the series? (Judging sentiment using automatic sentiment analysis.)

## Week 11 Update
- I decided to work with the transcripts of the TV show Cheers. While the data is not as available as for the TV show The Office, I enjoyed the challenge of compiling the data and cleaning it up.
- I obtained data from two different sources. The first source was [this website](https://subslikescript.com/series/Cheers-83399) which gave me the transcripts of all episodes in the series. I wrote my own java code that uses the Jsoup library to download the individual lines directly from the website. In this step I recorded the line, the season and episode number, and the name of the episode. Last week I mentioned that there were some errors such as the letter "l" being in places where the letter "I" should be sometimes. I wrote my own java code that fixed many of these errors. I also got information from IMDb using Jsoup and my own java code. This was more difficult however because the website doesn't just use html to work. I was able to easily download the loaded page as html and then parse and clean the information from there. This is how I got the information on air date, rating, and number of votes for that rating. I then wrote some more java code that combined these two datasets into a single csv file (using a semicolon as the delimiter) with 111,697 rows and 7 columns. There is one line on each row, and the columns are organized as: line text, season number, episode number, episode title, air date, rating (out of 10), and the number of people that voted for that rating.
- One limitation with this dataset is that I do not know which character is speaking the line. This means I can not do specific character dialogue analysis like seeing if Norm says the word "beer" more than the average character on the show. I see this as an interesting challenge and I think that I will be able to get meaningfull data in different ways such as seeing if Norm's name appears more often than other names in the sentences around one that includes the word "beer."
- I have already found interesting things about even just the frequency of the names of characters. For example, "Norm" is spoken 1421 times and "Norman" is spoken 156 time, while "Cliff" is spoken 1114 times and "Clifford" is spoken 94 times. Norm's name is not only spoken more than Cliff's, but when people say Norm's name,  ~10% of the time they say his full first name while when people say Cliff's name, ~8% of the time they say his full first name.

## Departure Delays Map
<iframe
  src="Alaska_destinations_delays.html"
  width="100%"
  height="300"
  frameborder="0">
</iframe>

## Week 12 Update

- Since I started working with this dataset, I have been wondering if there really is a correlation between Norm and beer that is reflected purely in the dialogue. (In the show, Norm is a lover of beer.) I used a python function to determine the correlation after I had found the instances of each character's name as well as the word beer. I also widdened the range of lines that would be considered related to the character names. By that I mean that if Norm was mentioned in line 5, I would also include lines 4 and 6 as lines that are related to Norm. Also, for each character, I made sure to also include their last name when looking for instances of thier name appearing.

### Week 12 Visualization
<iframe
    src="beer_correlation.html"
    width="100%"
    height="300"
    frameborder="0">
</iframe>

