# Newsmap
Combines Google Maps’ functionality with data from Google News in order to create a website that enables users to search for webarticles atop a map.
<br><br>
"Mashup", a problem set from the HarvardX CS50 course, provides the foundation code for this project. For more information, click [here](https://docs.cs50.net/problems/mashup/mashup.html).  
## Background
This project uses Google Maps' APIs, particularly **[Google Maps JavaScript API](https://developers.google.com/maps/documentation/javascript/overview)**, to design the web app. The notation of "drawing on the map" (displaying webarticles) was partly accomplished using _[markers](https://developers.google.com/maps/documentation/javascript/markers)_.
<br><br>
The informational web articles themselves however, are fetched via **Google News**. It is noteworthy to mention that the articles' links and their respective titles were retrieved _without_ any "scraping". An [RSS](https://rss.com/blog/how-do-rss-feeds-work/) (Really Simple Syndication) feed was used instead.

## Project Files
### index.html
In addition to listing all the CSS & JS libraries, this file comprises of a _map-canvas_ of type 'id' onto which the entire newsmap is injected. The form simply takes user input. 
### styles.css
This file consists of the basic, default UI that was provided in the source code on the course page.
### scripts.js
This file relies on Google Map and mainly employs the global variables - _map, markers, info_ - to implement the "front-end" UI of the Newsmap.
<br><br>
Moving on, the script contains an anonymous function that - when fully loaded into memory by the DOM - is called by jQuery. Other noteworthy functions are _styles_ and _canvas_.
<br><br>
In addition to the funcitons _addMarker_ and _removeMarker_, which do precisely what they suggest, the _configure_ function defines the sequence of actions that take place upon certain 'event listening'. Finally, the _search, showInfo,_ and _update_ functions are reminiscent of their names as well.
### application.py
The crux of the Newsmap, written in Python. _Articles_ is implemented in a manner such that it returns a JSON array of objects, each of which represents an article that is eventually used as a GET parameter; whereas search outputs JSON arrayed objects that represent a row of places and are matched to the _q_ (the search query).
### helpers.py
A helper file provided with the problem set material containing the _lookup_ function that queries the Google News articles for a particular geography (country specific: USA). 
### mashup.db
Made a la **phpLiteAdmin**,  this database contains a table called _places_ with 12 fields  geographically label news articles.
