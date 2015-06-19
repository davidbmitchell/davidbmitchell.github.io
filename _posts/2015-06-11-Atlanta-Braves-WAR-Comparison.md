---
title: Atlanta Braves WAR Comparison
layout: post
category: MLB
tags: [Atlanta Braves, openWAR, R]
---

The Atlanta Braves have had an interesting season to say the least. Coming into 
this year they traded away many of their best performers from last season. This 
led a lot of the pundits (including myself) to conclude the Braves were going to 
struggle mightily this season. So far we wrong as the Braves sit at 29-30 and just 
2.0 games back as of June 10. Their record would undoubtably be better if their 
relievers had not blown a few games this year. This is evident by the fact their 
relief pitching ranks 29th in RA/G (4.41), and in the table listing WAR values 
below shows most of the Braves' players which have been performing below 
replacement level are relievers.

# The Comparison
The table below compares how the players for the Atlanta Braves have done with 
regards to Wins Above Replacement. Baseball-Reference.com WAR is denoted by bWAR, 
FanGraphs.com WAR by fWAR, and the open-source version of WAR (openWAR) that 
uses R and the MLB Gameday API is denoted by oWAR. The repository for openWAR can
be found on [GitHub](https://github.com/beanumber/openWAR). The academic 
paper written by the creators Ben Baumer and Gregory Matthews, which explains openWAR 
better than I am able to, can be found [here](http://arxiv.org/pdf/1312.7158v3.pdf).
bWAR and oWAR include games up to June 9th and fWAR contains games up to 
June 10th. Also, the table is sortable.

<table class="sortable" style="margin: 0px auto;">
    <tr>
        <th>Player</th>
        <th>Position</th>
        <th>bWAR</th>
        <th>fWAR</th>
        <th>oWAR</th>
    </tr>
    <tr>
        <td>Freddie Freeman</td>
        <td>1B</td>
        <td>1.65</td>
        <td>1.7</td>
        <td>2.95</td>
    </tr>
    <tr>
        <td>Cameron Maybin</td>
        <td>CF</td>
        <td>0.93</td>
        <td>1.3</td>
        <td>2.1</td>
    </tr>
    <tr>
        <td>Jace Peterson</td>
        <td>2B</td>
        <td>1.13</td>
        <td>1.1</td>
        <td>1.74</td>
    </tr>
    <tr>
        <td>Shelby Miller</td>
        <td>SP</td>
        <td>2.95</td>
        <td>1.2</td>
        <td>1.73</td>
    </tr>
    <tr>
        <td>Alex Wood</td>
        <td>SP</td>
        <td>1.32</td>
        <td>1.6</td>
        <td>1.39</td>
    </tr>
    <tr>
        <td>Nick Markakis</td>
        <td>RF</td>
        <td>0.59</td>
        <td>1.1</td>
        <td>1.25</td>
    </tr>
    <tr>
        <td>A.J. Pierzynski</td>
        <td>C</td>
        <td>-0.44</td>
        <td>0.5</td>
        <td>1.03</td>
    </tr>
    <tr>
        <td>Kelly Johnson</td>
        <td>UT</td>
        <td>0.54</td>
        <td>0.7</td>
        <td>1.02</td>
    </tr>
    <tr>
        <td>Andrelton Simmons</td>
        <td>SS</td>
        <td>1.52</td>
        <td>1.4</td>
        <td>0.85</td>
    </tr>
    <tr>
        <td>Todd Cunningham</td>
        <td>OF</td>
        <td>0.44</td>
        <td>0.4</td>
        <td>0.61</td>
    </tr>
    <tr>
        <td>Jonny Gomes</td>
        <td>LF</td>
        <td>-0.31</td>
        <td>-0.5</td>
        <td>0.59</td>
    </tr>
    <tr>
        <td>Luis Avilan</td>
        <td>RP</td>
        <td>0.39</td>
        <td>0.3</td>
        <td>0.53</td>
    </tr>
    <tr>
        <td>Chris Johnson</td>
        <td>3B</td>
        <td>-0.24</td>
        <td>-0.1</td>
        <td>0.35</td>
    </tr>
    <tr>
        <td>Brandon Cunniff</td>
        <td>RP</td>
        <td>0</td>
        <td>0.1</td>
        <td>0.34</td>
    </tr>
    <tr>
        <td>Williams Perez</td>
        <td>SP</td>
        <td>0.56</td>
        <td>0.5</td>
        <td>0.28</td>
    </tr>
    <tr>
        <td>Michael Kohn</td>
        <td>RP</td>
        <td>0.18</td>
        <td>0</td>
        <td>0.23</td>
    </tr>
    <tr>
        <td>Juan Uribe</td>
        <td>3B</td>
        <td>0.29</td>
        <td>0.2</td>
        <td>0.23</td>
    </tr>
    <tr>
        <td>Mike Foltynewicz</td>
        <td>SP</td>
        <td>-0.06</td>
        <td>0.5</td>
        <td>0.16</td>
    </tr>
    <tr>
        <td>Phil Gosselin</td>
        <td>UT</td>
        <td>0.27</td>
        <td>0.3</td>
        <td>0.13</td>
    </tr>
    <tr>
        <td>Jim Johnson</td>
        <td>RP</td>
        <td>0.07</td>
        <td>0.1</td>
        <td>0.12</td>
    </tr>
    <tr>
        <td>Jason Grilli</td>
        <td>RP</td>
        <td>0.01</td>
        <td>0.4</td>
        <td>0.11</td>
    </tr>
    <tr>
        <td>Eric Young</td>
        <td>CF</td>
        <td>-0.59</td>
        <td>-0.6</td>
        <td>0.04</td>
    </tr>
    <tr>
        <td>Andrew McKirahan</td>
        <td>RP</td>
        <td>0</td>
        <td>0.1</td>
        <td>0.04</td>
    </tr>
    <tr>
        <td>Pedro Ciriaco</td>
        <td>UT</td>
        <td>0.12</td>
        <td>-0.1</td>
        <td>0</td>
    </tr>
    <tr>
        <td>Juan Jaime</td>
        <td>RP</td>
        <td>-0.04</td>
        <td>-0.1</td>
        <td>-0.07</td>
    </tr>
    <tr>
        <td>Nick Masset</td>
        <td>RP</td>
        <td>-0.26</td>
        <td>-0.3</td>
        <td>-0.08</td>
    </tr>
    <tr>
        <td>Cody Martin</td>
        <td>RP</td>
        <td>-0.31</td>
        <td>-0.2</td>
        <td>-0.09</td>
    </tr>
    <tr>
        <td>Sugar Marimon</td>
        <td>RP</td>
        <td>-0.18</td>
        <td>-0.1</td>
        <td>-0.12</td>
    </tr>
    <tr>
        <td>Joey Terdoslavich</td>
        <td>OF</td>
        <td>-0.1</td>
        <td>0.1</td>
        <td>-0.17</td>
    </tr>
    <tr>
        <td>John Cornely</td>
        <td>RP</td>
        <td>-0.13</td>
        <td>-0.1</td>
        <td>-0.3</td>
    </tr>
    <tr>
        <td>Christian Bethancourt</td>
        <td>C</td>
        <td>0.35</td>
        <td>-0.2</td>
        <td>-0.3</td>
    </tr>
    <tr>
        <td>Donnie Veal</td>
        <td>RP</td>
        <td>-0.41</td>
        <td>-0.4</td>
        <td>-0.39</td>
    </tr>
    <tr>
        <td>Julio Teheran</td>
        <td>SP</td>
        <td>-0.6</td>
        <td>-0.3</td>
        <td>-0.73</td>
    </tr>
    <tr>
        <td>Trevor Cahill</td>
        <td>RP</td>
        <td>-0.77</td>
        <td>-0.1</td>
        <td>-1.17</td>
    </tr>
</table>

# The Code
I gathered all this information using the R programming language and RStudio. 
I will walk you through how I performed the operations. 

First, we must install the openWAR and openWARData R packages and then load 
them, and we will need the dplyr package as well.
{% highlight r %}
devtools::install_github("beanumber/openWAR")
devtools::install_github("beanumber/openWARData")
library(openWAR)
library(openWARData)
library(dplyr)
{% endhighlight %}

After we have all the packages we need installed, we can download our play by 
play data using openWAR, and then make the open-source version of WAR. It must 
be noted this will take a little while depending on your internet conncection.
{% highlight r %}
MLBAM2015 <- getData(start="2015-04-05", end="2015-06-09")
# make oWAR
ds <- makeWAR(MLBAM2015)
# tabulate oWAR
oWAR <- getWAR(ds$openWAR)
{% endhighlight %}

Next, we can download the data from Baseball-Reference using the getrWAR() 
function from the openWARData package. To get the FanGraphs WAR we can use 
the [getfWAR()](/assets/getfWAR.R) function I wrote. 
Also, let's go on and download playerID map from [Crunch Time Baseball](http://crunchtimebaseball.com).
{% highlight r %}
rWAR <- getrWAR()
fWAR <- getfWAR(2015)
id <- read.csv("http://crunchtimebaseball.com/master.csv")
# We only need the mlb_id, bref_id, and fg_id 
id <- select(mlb_id, bref_id, fg_id)
{% endhighlight %}

Now that we have all the data, it is just a matter of putting it all together.
{% highlight r %}
# filter rWAR so that only this year's Atlanta Braves WAR is included
rWAR <- filter(rWAR, yearId == 2015, teamId == "ATL")
# merge rWAR and playerIDs
braves <- merge(rWAR, id, by.x="playerId", by.y = "bref_id")
# merge braves and fWAR
braves <- merge(braves, fWAR, by.x="fg_id", by.y="playerId")
# merge braves and oWAR
braves <- merge(braves, oWAR, by.x="mlb_id", by.y="playerId")
# finally select only the columns that are interesting 
# you do not have to do this, it just makes the data cleaner
braves.WAR <- select(braves, Name, rRAA_bat, rRAA_field, rRAA_pitch, rWAR, 
                            fRAA_bat, fRAA_br, fRAA_field, fWAR_pitch, fWAR, 
                            RAA.br, RAA.off, RAA.field, RAA.pitch, WAR )
{% endhighlight %}
