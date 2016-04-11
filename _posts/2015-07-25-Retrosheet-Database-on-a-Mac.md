---
layout: post
title: "Building Retrosheet Database on a Mac"
date: "2015-07-25"
tags: [MLB, Retrosheet, SQL]
permalink: /blog/2015-07-25-Retrosheet-Database-on-a-Mac
---

Okay, this post is going to be a long one, but by the end of it, you will have
created yourself a Retrosheet database for MySQL or MariaDB. There is a post
similar to this on [Beyond the Boxscore](http://beyondtheboxscore.com)
called [Saberizing a Mac #9: Retrosheet (part1)](http://www.beyondtheboxscore.com/2013/2/14/3982712/saberizing-a-mac-9-retrosheet-part-1);
however, it is severely lacking details on how to get the database actually
set up your Mac.

# Installing Homebrew
In order to parse the .EVN and .EVA event files from Retrosheet, we need to
install the [Chadwick](http://chadwick.sourceforge.net/doc/index.html) tools.
Before we can do that we need to install Homebrew which is a package manager
for OSX.

### Download XCode for Mac
You can install XCode directly from the [Mac App Store](https://itunes.apple.com/us/app/xcode/id497799835?mt=12). We need this
to install the command-line tools.

### Get the Command-Line Tools
Open up your terminal which is located in ```/Applications/Utilities/```, and in
the terminal run the following command.
{% highlight bash %}
$ xcode-select --install
{% endhighlight %}
### Install Homebrew
Now that we have the command-line tools, we can finally download and install
Homebrew. Keep your terminal app open and run:
{% highlight bash %}
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
{% endhighlight %}
Once, it is installed run ```brew doctor``` and if you get the message
```Your system is ready to brew``` you are golden. If you do not, this
[post](http://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/#troubleshoot-brew)
is an excellent troubleshooting resource.

# Install MariaDB
If you already have MySQL or MariaDB installed on your computer, you can skip
this section and move onto installing Chadwick.
Once we have homebrew installed we can build MariaDB which is a fork of MySQL
that has better performance. Reasons for choosing MariaDB over MySQL can be
found [here](https://mariadb.com/kb/en/mariadb/mariadb-vs-mysql-features/).
To install we run:
{% highlight bash %}
$ brew install mariadb
{% endhighlight %}
Once that is completed run:
{% highlight bash %}
$ unset TMPDIR
$ mysql_install_db
{% endhighlight %}
You can make it so every time you log in to your computer the MariaDB/MySQL server
starts up, but I prefer to start it manually any time I need it. To start it
all you have to do is run in your terminal.
{% highlight bash %}
$ mysql.server start
{% endhighlight %}
Once you start up the server, you logging in is very easy.
{% highlight bash %}
$ mysql -u root
{% endhighlight %}

# Install Chadwick
A couple weeks ago I was finally able to get Chadwick added to Homebrew. This makes
installing the it so much easier on a Mac.
{% highlight bash %}
$ brew install chadwick
{% endhighlight %}
Chadwick is an open-source program that allows one to parse the event files
from Retrosheet. Suppose I have the event files from the 2014 season, which can
be downloaded directly from [Retrosheet](http://www.retrosheet.org/events/2014eve.zip).
I then unzip the files and navigate into the directory in which it was unzipped.


I am interested in the Braves home opener from 2014, which was against the
New York Mets. Using the chadwick tool ```cwbox```, I am able to print out the boxscore
from that game to my terminal. The steps below illustrate how this is accomplished.
{% highlight bash %}
$ cd ~/Downloads/eve2014
$ cwbox -h

Chadwick boxscore generator, version 0.6.4
  Type 'cwbox -h' for help.
Copyright (c) 2002-2014
Dr T L Turocy, Chadwick Baseball Bureau (ted.turocy@gmail.com)
This is free software, subject to the terms of the GNU GPL license.



cwbox generates boxscores from play-by-play files
Usage: cwbox [options] eventfile...
options:
  -h        print this help
  -i id     only process game given by id
  -y year   Year to process (for teamyyyy and aaayyyy.ros).
  -s start  Earliest date to process (mmdd).
  -e end    Last date to process (mmdd).
  -X        output boxscores as XML.
  -S        output boxscores as SportsML.
  -q        operate quietly; do not output progress messages

$ cwbox -i ATL201404080 -y 2014 2014ATL.EVN

Chadwick boxscore generator, version 0.6.4
  Type 'cwbox -h' for help.
Copyright (c) 2002-2014
Dr T L Turocy, Chadwick Baseball Bureau (ted.turocy@gmail.com)
This is free software, subject to the terms of the GNU GPL license.

[Processing file 2014ATL.EVN.]
     Game of 4/8/2014 -- New York at Atlanta (N)

  New York           AB  R  H RBI    Atlanta            AB  R  H RBI
Young E, lf           4  0  2  1   Heyward J, rf         5  0  0  0
Murphy D, 2b          5  0  1  0   Upton B, cf           4  0  1  0
Wright D, 3b          5  0  0  0   Freeman F, 1b         4  0  1  0
Granderson C, rf      2  0  0  0   Johnson C, 3b         4  0  1  0
Duda L, 1b            4  1  1  0   Upton J, lf           4  0  2  0
Lagares J, cf         4  0  1  0   Uggla D, 2b           4  0  1  0
d Arnaud T, c         4  1  2  0   Gattis E, c           4  0  1  0
Tejada R, ss          3  2  2  2   Simmons A, ss         4  0  1  0
Colon B, p            2  0  0  0   Harang A, p           2  0  0  0
Davis I, ph           1  0  0  0   Schlosser G, p        0  0  0  0
Farnsworth K, p       0  0  0  0   Avilan L, p           0  0  0  0
Valverde J, p         0  0  0  0   Varvaro A, p          0  0  0  0
                                   Doumit R, ph          1  0  0  0
                                   Thomas I, p           0  0  0  0
                                   Beato P, p            0  0  0  0
                                   Laird G, ph           1  0  0  0
                     -- -- -- --                        -- -- -- --
                     34  4  9  3                        37  0  8  0

New York         001 000 210 --  4
Atlanta          000 000 000 --  0

  New York             IP  H  R ER BB SO
Colon B (W)           7.0  6  0  0  0  5
Farnsworth K          1.0  0  0  0  0  1
Valverde J            1.0  2  0  0  0  0

  Atlanta              IP  H  R ER BB SO
Harang A (L)          6.0  2  1  1  4  9
Schlosser G           0.1  2  2  2  0  0
Avilan L              0.1  2  0  0  0  0
Varvaro A             0.1  0  0  0  0  0
Thomas I              0.1  2  1  1  0  0
Beato P               1.2  1  0  0  0  0

E -- Tejada R, Valverde J
LOB -- New York 8, Atlanta 10
2B -- Freeman F, d'Arnaud T
SB -- Young E 2, Granderson C
SH -- Colon B
WP -- Harang A
T -- 3:07
A -- 47144
{% endhighlight %}

# Building Your Retrosheet Database
Okay, we are finally ready to begin building the retrosheet database. First 
download [this zip file](/assets/Retrosheet.zip) which contains the sql files
we will need and empty folders named unparsed and parsed. Unzip this file
into your home directory. The unparsed folder
is what we will download the Retrosheet event files into, and the parsed folder
will contain the csv's after we parse the event files. Here is what the retrosheet
folder tree will look like.
{% highlight bash %}
# We want the Retorhseet folder in the home directory
$ cd ~/Retrosheet
$ tree .
.
├── parsed
├── sql
│   ├── 01_schema.sql
│   ├── 02_load_events.sql
│   ├── 03_load_games.sql
│   ├── 04_load_subs.sql
│   ├── 05_partition.sql
│   └── 06_lookup_codes.sql
└── unparsed
{% endhighlight %}

Once again I recommend moving the unzipped folder after you download it into your home 
directory because the loader sql files tell the database server to look for
the data in ~/Retrosheet/parsed/. If you want this folder somewhere else you'll
have to edit the sql loader files.

### Downloading the Data
We can actually download the data directly from Retrosheet using the terminal and
wget. This really makes it easier than downloading them indiviudally. Follow the 
steps that are shown below to download the data zip files by decade, beginning with
the 1950's. Once we download them, we will unzip the files as well.
{% highlight bash %}
# make sure we are in the Retrosheet/unparsed directory
$ cd ~/Retrosheet/unparsed
$ startDecade=1950 endDecade=2010
$ while [$startDecade -le $endDecade ]; do
while> wget http://www.retrosheet.org/events/"$startDecade"seve.zip
while> let startDecade=startDecade+10
while> done
$ find . -name "*.zip" -exec unzip {} \; -exec /bin/rm {} \;
{% endhighlight %}
If you open up the unparsed folder in your finder you will find a folder full of 
.EVA, .EVN, and .ROS files. These are the Retrosheet files that Chadwick will parse.

### Parsing the Data
Since we now have all the data we need, we can finally start parsing the data.
Using three for loops in your terminal will allow us to parse all the data from 1950
to 2014. One loop parses the events, the games, and the subs into csv files that
can be loaded into the database.
{% highlight bash %}
# make sure we are still in the unparsed directory
$ cd ~/Retrosheet/unparsed
$ x=1950 y=2014
$ for (( i=$x; i<=$y; i++ )); do cwevent -f 0-96 -x 0-62 -y "$i" "$i"*.EV* > ~/Retrosheet/parsed/all"$i".csv; done
$ for (( i=$x; i<=$y; i++ )); do cwgame -f 0-83 -y "$i" "$i"*.EV* > ~/Retrosheet/parsed/games"$i".csv; done
$ for (( i=$x; i<=$y; i++ )); do cwsub -f 0-9 -y "$i" "$i"*.EV* > ~/Retrosheet/parsed/sub"$i".csv; done
{% endhighlight %}

### Creating and Populating the Retrosheet Database
Using the sql files that are included in the zip file, we can create and populate
the Retrosheet database. The first script, <b>01_schema.sql</b> defines the Retrosheet
database schema. It creates an events_bck, events, games_bck, games, and subs tables.
The events_bck and games_bck tables are what we will load the data into using 
<b>02_load_events.sql</b> and <b>03_load_games.sql</b>. We load the subs into the subs table 
using <b>04_load_subs.sql</b>. To insert the data from events_bck and games_bck into the events
and games tables we use the <b>05_partition.sql</b>. In this file we create the "YEAR_ID"
columns which the tables are patitioned by and copy the rows from the two loader
tables into our final tables. Lastly, our lookup tables are stored in <b>06_lookup_codes.sql</b>. This
also contains the players table which holds all the player ID's from each player in the Retrosheet
data.

The structure for these tables is suggested by Colin Wyers from the Hardball Times,
and all I did was make modifications that would make the files compatiable on a Mac.
His orginial post is entitled [Building a Retrosheet Database, the Short Form](http://www.hardballtimes.com/tht-live/building-a-retrosheet-database-the-short-form/).

In the code below, you can see that our first step is to start the mysql server.
The next step creates the Retrosheet schema, and the others populate the database.
Notice the <b>--local-infile=1</b>; we have to add this because this feature
has been disabled by default because of [security issues](https://dev.mysql.com/doc/refman/5.1/en/load-data-local.html).
Using that flag though allows it temporarily, and rest assured there is nothing
in those sql scripts that should cause you any worry.

{% highlight bash %}
$ mysql.server start
$ mysql -u root <- ~/Retrosheet/sql/01_schema.sql
$ mysql --local-infile=1 -u root < ~/Retrosheet/sql/02_load_events.sql
$ mysql --local-infile=1 -u root < ~/Retrosheet/sql/03_load_games.sql
$ mysql --local-infile=1 -u root < ~/Retrosheet/sql/04_load_subs.sql
$ mysql -u root < ~/Retrosheet/sql/05_partition.sql
$ mysql -u root < ~/Retrosheet/sql/06_lookup_codes.sql
{% endhighlight %}

We do not have to specify a database because each of the loader sql scripts
include the following in the first line.
{% highlight mysql %}
USE `retrosheet`;
{% endhighlight %}
As a side note, if you created a password for your server (which is not covered here
because this database is meant to remain local), you will have to use the <b>-p</b>
flag. 

At this point you should have a Retrosheet database on your Mac. If these steps did not work,
you found any errors, want more elaboration, or have any other general questions please email
me at <a href="mailto:david.b.mitchell@icloud.com">david.b.mitchell@icloud.com</a>. In future posts
I will demonstrate some of the SQL queries you can perform using the Retrosheet data.

