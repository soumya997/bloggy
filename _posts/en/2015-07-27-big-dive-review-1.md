---
layout: post
comments: true
name: bigdive-1
title: Big Dive review, part I
---

Three weeks ago I came back from [Big Dive](www.bigdive.eu), a five week course in data science. It is run every summer by [TOP-IX](http://www.top-ix.org/en/) in Turin, Italy. The organisers decided to teach us three broad *tracks*: visualisation, development and data science. Apart from regular lectures, every week we had a few invited guests who gave *external* talks. The course has been successful so far, I expect the next edition to happen in 2016. This post is a summary/review of the 2015 (fourth) edition and is meant to help you if you are thinking about becoming a *Diver* in the future.

To give you a better idea, let me first list my relevant skills.

**Coding**: As a physicist, I am familiar with many programming environments, but I have not mastered any of them. I am most fluent in Python, which I genuinely like and I sometimes write side projects in it (see my github).

**Data science**: A couple of months before Big Dive I had taken "The Analytics Edge", a great data science course on edX.org. I learned the basics of several machine learning techniques, I even participated in a Kaggle competition, so I had an idea what it was all about.

**Visualisation**: No experience here. I can use matplotlib and I care about the quality of my plots more than an average scientist, but that's it.

In this post, I will focus on *internal* courses, which took the best part of our days in Turin (~5h in class). I will review external talks and the final project on another occasion.

# Visualisation
teacher: **Fabio Franchino** ([@fabiofranchino](https://twitter.com/fabiofranchino))

<br />

We used only one tool: [d3.js](http://d3js.org/). Given the enormous capabilities of the library, it was a very reasonable choice. Fabio was by far the best teacher on the course. His method was to show us a feature (like drawing a circle on an svg object or making transitions), then to set a similar exercise for us. He would then walk around the class and help people out, and after some time he'd present the solution on the projector. At the end of the week, he gave us four hours to work in pairs on a visualisation of our choice, based on a dataset of Sochi Winter Olympics medals.

Result: in order to wield d3.js efficiently, you have to [change how you think](http://bost.ocks.org/mike/join/) about coding, as objects in d3 are linked to data. The first week of Big Dive definitely helped me with this mindset change. Before the course, I had not known what d3 was. Now I can write good-looking visualisations, albeit with some googling along the way. Still, proper nesting hurts my brain.

# (Python) Development

teacher: **Alessandro Molina** ([@\_\_amol\_\_](https://twitter.com/__amol__))

<br />

This course was focused on Python and its modules only as programming tools. I think you can get the most of it if you already [speak some Python](http://themetapicture.com/harry-speaks-python/) so you don't have to waste your time and attention on trivial mistakes. We had a few lessons about more advanced features: generators, decorators, profiling, etc. If you are a scientist like me, you probably don't use them, but they are very helpful for working with big data. We focused on the following tools, ordered by the amount of time allocated to them:

#### MapReduce

If you have not heard about it, MapReduce is a way to process big amounts of data using multiple processes (and much more than this).

On Alessandro's courses, you'll gain a good understanding of the algorithm. We started by writing our own Map Reduce class and modifying it — what better way of getting to the bottom of things? You will also be able to run a MapReduce job on an external service, such as AWS. I don't fully agree with the choice of tool for the course (MrJob) because I think there are better alternatives (e.g. [Spark](http://spark.apache.org/docs/latest/api/python/pyspark.html)), but once you learn the concept, it is easy to learn other tools.

#### MongoDB

There are 2-3 lessons about MongoDB, of which I also had had zero knowledge. Despite being impressed by a NoSQL database, I did not use it in the final project (the data were not big enough). However, Alessandro left very well documented Ipython notebooks for us, so I can always revisit.

#### WSGI

We also spent some time on integrating our python scripts with the Web. You can for example parse a stream of real-time data, make a d3.js plot visualisation of these data and update it continuously. Again, I haven't used it in the final project, but I like the idea a lot.

_____

Result: I am confident with Map Reduce now, especially after taking the Spark course on edX (CS100.1x). There was not as much depth in MongoDB and WSGI parts, so I would have to read about them more before making use of them. Again, I can always go back to the excellent notebooks, and at least I know what contexts to use MongoDB/WSGI in. 

### Data Science
teachers: **André Panisson** ([@apanisson](https://twitter.com/apanisson)), **Michele Tizzoni** ([@mtizzoni](https://twitter.com/mtizzoni)), **Laetitia Gauvin** ([@laetitiagvn](https://twitter.com/laetitiagvn))

<br />

This was the most interesting part for me, and really what I came to Turin for. On the first days we had a comprehensive intro/recap of stats with Michele, which is obligatory knowledge for any aspiring data scientist (where do you think the name _statistical learning_ came from?). Obviously we didn't have time to go through all machine learning techniques, so André decided to focus on:

* regression techniques
* text analytics (running a TF-IDF algorithm, also analysing Twitter stream)
* classification (e.g. with [support vector machines](https://en.wikipedia.org/wiki/Support_vector_machine))
* dimensionality reduction with [PCA](http://setosa.io/ev/principal-component-analysis/)

All lessons about the above techniques were accompanied by exercises, so I could grasp the idea easily. In order to really understand their mathematical foundations however, I had to dig a little deeper. For PCA, I recommend the slides and the exercise from CS190.1x course on edX.org (Scalable Machine Learning).

After ML, we turned to network science. The theory was explained by Laetitia, and then André showed us [NetworkX](https://networkx.github.io/), a Python module for analysing networks. Network science was completely new to me, so the concepts that we learned were interesting, but I am still skeptical about their predictive value. I had an impression that it might be good for simplifying and visualising a very complex system, but then the results are always open for many interpretations.

### Summary

I would say Big Dive is a good course for you if:

* you are looking for a broad, not necessarily deep, introduction to data science
* you know enough Python so you don't waste time on fixing trivial mistakes
* you are interested in data visualisation in d3.js, as this is possibly the best prepared part of the course
* you would like to learn about big scale data processing (MongoDB, MapReduce)
* you have some knowledge about machine learning, but you'd like to learn more about the most popular techniques
* you want to do social network analysis — we had very competent teachers
* you are looking for a data science job **in northern Italy** (almost all external speakers said their institutions were hiring)

My main criticism of the course were set-up glitches: we sometimes had to wait half an hour for everyone to successfully install a module. It is upsetting because Python's virtualenvs have exactly this purpose: to ensure compatibility. We could have been given a prepared, working environment. Anyway, I complained about it a few times to the organisers, and they were responsive, so I hope this will be avoided in the next editions.

Finally, I'd like to reiterate that we had **excellent** teachers. You could tell they genuinely wanted to pass on us some of their knowledge (believe me, I have attended other courses, and this is not always the case). No question was left unanswered!