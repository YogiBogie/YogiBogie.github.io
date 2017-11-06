---
layout: post
title:      "How I Conquered My Fear of Ruby CLI GEM"
date:       2017-11-06 22:54:08 +0000
permalink:  how_i_conquered_my_fear_of_ruby_cli_gem
---


"How am I going to get this thing to work" - Me

That's a phrase I used a lot while trying to figure out how to scrape a website and setup a functional CLI.  

I decided that I would scrape NBCNEWS.com for my project since it's a site I'm familiar with.  I knew that my scraper would need to have three parts.  The first part would be to scrape the homepage for the title of all the headlines on the page, then scrape the articles listed under each headline and finally scrape the article's webpage for the content.

I watched the videos in the links posted at the bottom of the lesson page and was ready to start (or so I thought).

All went well at first, Headline title scraping?  No problem, easy enough:

![](https://i.imgur.com/W1OuzhN.png)

Article title scraping?  Sure that one's easy too!

![](https://i.imgur.com/byfFE8b.png)

Article paragraph scraping?  Ummmmm.

"How am I going to get this thing to work"?  

The issue being that the css code for the url to the article was about 2 parrallel levels before the title of the article in the source code. I racked my brains several times as to how I could get the url to the article when it came before the actual title of the article.  I tried different code but it while I could get it to work most of the time, there would always be some unique circumstance that would make the code I had fail. (Url and article title would not match, blank url or blank titles, etc.)

"Why can't I get this to work consistenlty!?"

Finally I figured it out, if I could store the css code for the entire group and then loop through every css row then I could grab both the title and the url for the article individually.

![](https://i.imgur.com/5lDmxXF.png)


The only thing left to do was scrape the article, but luckily for me there were very few differences between types of articles.  I was able to figure out that if it was a sports article they would go to the NBCSports site, if it was a video it would have the phrase '/video/" as part of its url or if it was a 'Mach' or 'Better' article they would have those words as part of the url.  Also, if it was a video then I wouldn't be able to scrape the article because it wasn't text based but I could show the url to the user so they can click and open it in their own browswer.  Once I had the plan of attack figured out I was then able to customize the scraping of the article based on the article's url.

![](https://i.imgur.com/NGQ1MyB.png)

Each one of the methods above calls a slightly different type of scraper method that looks for the correct CSS codes based on the type of article it is scraping.

"Finally!"
This proect took me a long time and was probably the hardest, most frustrating thing I've had to code so far.  But now that I've done it, the dread I felt when I was in the weeds is now surpassed by the amount of joy and pride I have that I was able to conquer this project!
