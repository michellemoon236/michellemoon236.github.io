---
layout: post
title:      "First Project: Disney Movies CLI"
date:       2019-05-19 00:37:26 +0000
permalink:  first_project_disney_movies_cli
---


My first project is a command line interface (CLI) program that scrapes from a webpage date source of a topic of my choosing. Being a kid at heart, I immediately thought of cartoons. I decided to do my CLI scraping project on Disney animated movies. One thing I love about Disney movies is how widespread their impact has been. When you ask someone the question: what Disney movie is your favorite? often that person’s face lights up and they know which one and why. It brings up fond memories for many people.

It was quite exciting and fulfilling to write my first program. Here are a few things I learned along the way.

**Scraping Technique**: Specific data from a website can be retrieved using Nokogiri and the .css method. One useful thing I learned while doing this project is instead of going straight to writing ruby code for scraping, you can first find the specific CSS selectors for scraping by using DevTools in the Google Chrome browser. In DevTools in the console tab, you can use the document.querySelectorAll function to pinpoint the data you are looking for. Using the DevTools first was a way to make scraping easier.

**What Website to Scrape**:  At first, I found it hard to find a website to scrape. What I was looking for was a very specific kind of website that has a list of the Disney movies all on one page and then clickable links to each specific movie. In the process of searching, I came across many websites that had a list of Disney movies but spread out on multiple pages in a slideshow type format. At first I discounted these lists, but then I discovered that sometimes a website may show multiple pages for something but when you inspect the website the information is actually all on one webpage. So the website I chose was one of these examples where the list scrolls to be on multiple pages but when scraping it all comes from one webpage. 

**Scraping Data OnlyOnce**: One problem I had to think through was how to write a program where each webpage was scraped only once. My program is written where it starts by displaying the list of all the Disney movies and asking if the user would like more details on a specific movie which would then result in scraping another webpage of that specific movie. If a user selected to view the details of one movie multiple times, how could the program be written so that one movie webpage is only scraped the first time? I discovered the solution is to store the information from the scrape as an object in a class (Movie Class). Certain data points for the movie such as runtime, description, and release date are only assigned as attributes to that movie’s instance object when that webpage is scraped. If the specific movie’s webpage has not been scraped yet, then the movie attributes for those certain data points would be nil. So with a simple if statement (see below) it solved the problem so the specific movie’s webpage is only scraped once even if called multiple times.  If that movie attribute from the specific movie's webpage already exists (example here: the movie’s runtime), the website is not scraped again and instead the program moves to the next line of code of printing out the details of the movie whose attributes have already been stored in its movie object from the scrape completed previously.

```
	Scraper.scrape_single_movie(single_movie) if !single_movie.runtime
	print_single_movie(single_movie)
```


