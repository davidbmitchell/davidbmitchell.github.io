---
title: Comparing the Jason Heyward/Shelby Miller Trade using openWAR, bWAR, and fWAR
layout: post
category: MLB
tags: [Atlanta Braves, openWAR]
---

For those who are not familiar with openWAR, it is a package for the data and statistics programming language R created by Ben Baumer and Gregory Matthews.  It allows us to download game data from the [MLBAM GameDay](http://mlb.mlb.com/mlb/gameday/) web application. Using an open-source implementation of wins above replacement. More information on how to use openWAR can be found at the
Exploring Baseball Data With R [blog](https://baseballwithr.wordpress.com/2014/03/17/introduction-to-openwar/).

## The Trade

One of the biggest moves this offseason was when Jason Heyward and Jordan Walden were traded from the Atlanta Braves to St. Louis Cardinals for Shelby Miller and minor league prospect Tyrell Jenkins. Obviously there were many differing opinions on the quality of the trade from the Atlanta Braves point of view. I understood the trade, but 1) did not completely believe the Braves front office saying Heyward had no interest in extension talks and 2) really had this kid-like love for Jason Heyward. However, these biased views of mine aside, I thought the trade would turn out well for Atlanta. 

So far, my gut feeling has been right with Jason Heyward's struggles so far this season. Walden has been good for the Cardinals, but is currently expected to miss 6-10 weeks with a muscle strain in his shoulder. As much as Heyward has struggled thus far, Shelby Miller has thrived. In his last start, Miller was one out away from a masterful no-hitter against the Miami Marlins. Now that we have that out of the way, let's look at how the three different implementations of WAR say about the trade.

<table style="margin: 0px auto;">
  <tr>
    <th>Player</th>
    <th>openWAR</th>
    <th>bWAR</th>
    <th>fWAR</th>
  </tr>
  <tr>
    <td>Shelby Miller<br></td>
    <td>1.52</td>
    <td>2.27</td>
    <td>1</td>
  </tr>
  <tr>
    <td>Jason Heyward<br></td>
    <td>0<br></td>
    <td>0.18</td>
    <td>0.2</td>
  </tr>
  <tr>
    <td>Jordan Walden<br></td>
    <td>0.56</td>
    <td>0.56<br></td>
    <td>0.4</td>
  </tr>
</table>
