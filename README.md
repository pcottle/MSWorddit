# MSWorddit

MSWorddit was my first Javascript project -- it essentially reskins the homepage of reddit (along with other functionality) into a Microsoft Word interface.

<img src="http://petercottle.com/miscPics/msworddit.png"/>

It serves the silly (and not-so-honorable) purpose of disguising reddit browsing during work.

## Video

A demo on how to use MSWorddit can be seen [here](http://www.youtube.com/watch?v=8mOxQ2y2BBI)

## Challenges

I knew that if this application was going to be popular, I would have no way of sustaining the amount of traffic the reddit community would generate. I needed some kind of way obtaining all the reddit stories directly from the browser in a cross-origin way (aka JSONP). Reddit's API at the time didn't have JSONP support, so I was out of luck doing it the old-fashioned / obvious way.

I realized though that Yahoo's YQL API can serve up the raw DOM tree for any page on the internet. If I could get the raw HTML of the reddit front page, I could extract out the links I needed and build up my own view inside the fake MSWord interface.

Extracting out the relevant information is a bit of a hack unfortunately -- I basically recurse through the provided DOM tree in a semi-intelligent way and aggressively parse out the titles, users, and destination links. I anticipate changes in the HTML by having a few try / catches that will force recursion to another part of the tree. The same method is used for comment pages.

Since the HTML format is subject to change, this method is fairly brittle (it was my first project afterall :D).

## Usage

The site still gets around [50,000 unique visitors](http://msworddit.com/awstats.html) per month at the time of writing, so I've left the server running for the time being, despite the code not being in the best shape.

## Functionality

You can change the subreddit displayed by editing the "font" field to a valid subreddit name and hitting enter. Comments for a post can be viewed by clicking on the link embedded in the filler text, and the document can be turned into (and back from) a text editor by clicking on the formatting buttons. All this functionality is demonstrated in the video as well (linked above).

## Reddit Thread

The original reddit thread which got 17,296 upvotes can be viewed [here](http://www.reddit.com/r/reddit.com/comments/j4xtk/for_all_you_redditors_going_to_work_tomorrow_i/). The puns in this thread are pretty good as well.

