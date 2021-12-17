
# Table of Contents

1.  [What is this?](#orgb9ab804)
2.  [Redrawing Google trend chart (07-13-2021)](#org8b6bcda)
3.  [Data science process (07-15-2021)](#org745aced)
4.  ["Teaching the tidyverse in 2021" (09-07-2021)](#org53703ce)
5.  [Data or graph checking projects (10-07-2021)](#org5f2debb)
6.  [From the sickbed (11-02-2021)](#org84bacfd)
7.  [Good-bye (12-17-2021)](#org45cdd92)
8.  [References](#org6e27781)



<a id="orgb9ab804"></a>

# What is this?

A place for irregular articles of possible interest to students of
the DSC 101 course, mostly to avoid lengthy emails and to park
content that I may want to develop later on time permitting.


<a id="org8b6bcda"></a>

# Redrawing Google trend chart (07-13-2021)

Spent an afternoon rekindling some skills. Mean to show this during
the introduction to datascience lecture but I probably won't get
to. All of this started with this [infographic](https://trends.google.com/trends/explore?date=all&q=data%20science,machine%20learning) from Google's trend
graph generator. I wanted to reproduce it using R, which took a
couple of hours because I was quite out of shape.


## The original from `trends.google.com`

![img](https://github.com/birkenkrahe/dsc101/blob/main/img/trends_google.png)


## Trends from raw data

![img](https://github.com/birkenkrahe/dsc101/blob/main/img/trends.png)

![img](https://github.com/birkenkrahe/dsc101/blob/main/img/avg.png)


### Download dataset as `csv` file

Look at dataset: first two lines are spurious. Delete by hand so
that the header line (column names) is the first line of the
table:

    Category: All categories
    
    Month,Data science: (Worldwide),Machine learning: (Worldwide)
    2004-01,12,13
    2004-02,15,24
    2004-03,7,21
    2004-04,5,16
    2004-05,9,22


### Upload as data frame using `read.table`

To use the `Month` column as dates for a time series, turn
`trends$Month` into date format Date conversion: this can be done
with the `anytime` package which must be installed and loaded. I
found out about this via [stack.overflow](https://stackoverflow.com/questions/44488439/format-year-month-to-posixct).


### Create line plot

Here is a [short tutorial](https://www.statology.org/how-to-plot-multiple-lines-data-series-in-one-chart-in-r/) on how to do this using the functions
`points()`, `lines()` and `plot()`. The code is below.

    ## read data from CSV file
    trends <- read.table(
        file="./data/multiTimeline.csv",
        header=TRUE,
        sep=",")
    
    ## convert Month column to Date format
    library(anytime)
    Month <- anydate(trends$Month)
    trends <- cbind(trends[,-1],Month)
    
    month <- trends$Month
    ds <- trends$Data.science
    ml <- trends$Machine.learning
    
    ## plot Data science search values
    plot(x=month,
         y=ds,
         xlab="years",
         ylab="Interest",
         ylim=c(0,max(c(ds,ml))),
         type="l",
         lty=1,
         col="blue")
    
    ## plot Machine learning search values
    lines(x=month,
          y=ml,
          lty=2,
          col="red")
    
    ## add a legend
    legend(x=month[1],
           y=85,
           legend=c("Data science","Machine learning"),
           lty=c(1,2),
           col=c("blue","red"))


### Code summary

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left"><code>read.table</code></td>
<td class="org-left">upload data as <code>data.frame</code></td>
</tr>


<tr>
<td class="org-left"><code>library()</code></td>
<td class="org-left">load R package</td>
</tr>


<tr>
<td class="org-left"><code>anytime::anydate()</code></td>
<td class="org-left">convert vector to <code>Date</code> format</td>
</tr>


<tr>
<td class="org-left"><code>cbind()</code></td>
<td class="org-left">attach column to <code>data.frame</code></td>
</tr>


<tr>
<td class="org-left"><code>$</code></td>
<td class="org-left">extract vector from <code>data.frame</code></td>
</tr>


<tr>
<td class="org-left"><code>&lt;-</code></td>
<td class="org-left">assign right hand to left hand side</td>
</tr>


<tr>
<td class="org-left"><code>plot()</code></td>
<td class="org-left">draw scatter plot</td>
</tr>


<tr>
<td class="org-left"><code>lines()</code></td>
<td class="org-left">draw line graph</td>
</tr>


<tr>
<td class="org-left"><code>barplot()</code></td>
<td class="org-left">draw barplot</td>
</tr>
</tbody>
</table>


## Barplot   code

For some simple examples, see this [short tutorial](http://www.sthda.com/english/wiki/bar-plots-r-base-graphs#basic-bar-plots).

    ## read data from CSV file
    trends <- read.table(
        file="./data/multiTimeline.csv",
        header=TRUE,
        sep=",")
    
    ## convert Month column to Date format
    library(anytime)
    Month <- anydate(trends$Month)
    trends <- cbind(trends[,-1],Month)
    
    month <- trends$Month
    ds <- trends$Data.science
    ml <- trends$Machine.learning
    
    ## create the barplot from averages
    barplot(height=c(mean(ds),mean(ml)),
    	names.arg=c("Data science","Machine learning"),
    	ylab="Average interest (2004-2021)",
    	col=c("blue","red"))


<a id="org745aced"></a>

# Data science process (07-15-2021)

I was digging around my notes made for an online test lecture on May
19, on "Exploring data with R" (see [presentation](https://github.com/birkenkrahe/dsc101/blob/main/wiki/talk_presentation.pdf) & [notes](https://github.com/birkenkrahe/dsc101/blob/main/wiki/talk_notes.pdf)), for an
update on a [data science overview lecture](https://github.com/birkenkrahe/dsc101/tree/main/2_datascience). For this talk, I had
developed the model shown in figure [11](#orgf94fbfc): there are two pathways
towards machine learning. One pathway relied more on coding and
algorithms (traditionally taught in CS programs), the other one
relied more on modeling and heuristics (traditionally taught in
maths and statistics programs).

![img](https://github.com/birkenkrahe/dsc101/blob/main/img/data_science.png)

The model suppresses a lot of detail, of course, in order to
emphasize the contrast between coding and modeling, e.g. many
applications outside of CS, e.g. bioinformatics in biology.

It came straight out of two lines of thought: one related to the
experience of a CS professor that some CS students with more than
average interest in mathematics wanted to specialize on data
science. The other one related to my experience with exploratory
data analysis as a way of solving hard, data rich problems for real
clients (see figure [14](#orge93477b)).

![img](https://github.com/birkenkrahe/dsc101/blob/main/img/righteda.png)

I added this to the other two data science workflow images that I
already had in the lecture. And I added yet another one (see figure
[16](#orgac648e5)), from a recent book on data analytics<sup><a id="fnr.1" class="footref" href="#fn.1">1</a></sup>. I really like
how everything comes back and returns to the "real world" here, and
the feedback loop provided by the data analysis "pipeline".

![img](https://github.com/birkenkrahe/dsc101/blob/main/img/ds_workflow.jpg)

This is interesting, because it emphasizes the origin of most data
from (digital) devices and sees EDA as a way of making decisions
using various techniques (discussed in the book). I don't like the
emphasis on "decisions", since "making decisions" as such is not a
priority (there is no alternative). I prefer the old-fashioned way
of looking at **problems** and trying to find **solutions**. I've also
used the trendy term "decision intelligence" (made popular by Google
et al.), but I think it overplays both "decisions" and
"intelligence".

Most data science problems may not lead to decisions, to change or
to anything worth calling "intelligent". This is probably because of
my training as a physicist, though later I worked with business
people, who like the "decisions" and "challenges" lines of argument
more than "problems" and "solutions" - I can't even remember
why. The prejudice back in the day when this lingo came up was that
"problems" sound too much as if you had a problem, with negative
connotations, while "challenges" sounded as if you were worthy of a
challenge, I suppose. Pointless to argue, since everyone know what's
what anyway - except perhaps newbies.

Enough said. I extracted these figures from their context and added
them to the lecture - will see in August if this makes any
difference or not<sup><a id="fnr.2" class="footref" href="#fn.2">2</a></sup>.


<a id="org53703ce"></a>

# "Teaching the tidyverse in 2021" (09-07-2021)

I've mentioned the "tidyverse" before. This morning, I read an
article (posted in RWeekly, the weekly aggregator of R news that you
should subscribe to) "Teaching the tidyverse in 2021"
([Cetinkaya-Rundel, 2021](#org8b2282c)), which upset me. I will briefly explain
why. The article mentions the 2020 series of the same title, which
begins with the claim that "updates to tidyverse packages are
specifically designed to make it easier for new learners to get
started with doing data science in R." ([Cetinkaya-Rundel, 2020](#org20a4e1b)).

Instead of a long rant (see Matloff's "TidyverseSceptic" for a
complete picture of the criticism), just look at the first figure,
which shows "the lifecycle stages of functions and packages in the
tidyverse". This is not a bad diagram at all, and it makes my point:
a beginner, a learner of R, someone who wants to do data science,
should not have to learn about package development mechanics:
"experimental" vs. "deprecated" vs. "superseded" vs. "stable" -
What? Exactly.

![img](./img/lifecycle.png)

Reader, R beginner, let me tell you: there is no "tidyverse"
beginner's approach to R. You may like it or leave it (I prefer to
leave it, for a number of reasons, though you may need to know it),
but it's not an alternate R universe, and it's not an alternative to
base R, no matter how many times the creators and contributors of
this package bundle may say so.


<a id="org5f2debb"></a>

# Data or graph checking projects (10-07-2021)

Many of the project proposals by the course participants are still
much too complex for my taste - the research questions need to be
cut down to doable size.

Not simple but highly effective are projects that don't do anything
else but check published data and their interpretation. I mentioned
a student project from last term. This team of Master students
focused on a graph published in The Economist. I have uploaded their
final report "Improve Visualization of Popular Support for Executive
Actions in the U.S." and the data ([Cai, Otlu and Rauenbusch,
2021](#orga201792)). It's a very good piece of work, created with a lot of effort
over a period of three months. Less would easily do for our course.

Here is a more recent data checking example that you might find
interesting, by [Matloff (2021)](#orgc4a0334). This highly opinionated data
checking post uses statistical arguments to check policy
decisions. From the conclusions:

> "The much-vaunted failure rate reduction from 40% to 8%, is not borne
> out by the data at all. The district cannot or will not show the
> details of those numbers, and they concede the numbers are not
> consistent with the data that the district did provide."

For many more [interesting applications and project ideas](https://github.com/birkenkrahe/ds101/blob/master/ds_bookmarks.md#orgb216e90), see my
2020 data science bookmarks file on GitHub.

And here's a 2020 list of useful sites for [finding free, public
datasets](https://towardsdatascience.com/useful-sites-for-finding-datasets-for-data-analysis-tasks-1edb8f26c34d) for EDA tasks.


<a id="org84bacfd"></a>

# From the sickbed (11-02-2021)

I've been too ill to teach for a couple of days (just a bad cold,
nothing to worry about but still debilitating). This hasn't stopped
me from hunting and gathering R examples. Here are a few recent
captures.


## Webscraping example

![img](./img/webscraping.png)

> "Webscraping with R was critical to the success of my research."

From a recent Master thesis. The author had to gather data from
many different online curricula and collect them as a table for
further analysis.

Source: [Rauenbusch J (2021)](#org324eab3).


## New CRAN packages

(Via [`RWeekly.org`](https://rweekly.org/2021-W44.html), which you should subscribe to!)

![img](./img/chaos.png)

/Image: chaos machine setup - original is clickable ([Wilke, 2021](https://urssblogg.netlify.app/post/2020-11-19-synthesizing-temperature-measurements-into-sound/))

-   `cfbfastR`: Functions to Access College Football Play by Play
    Data (lvl=2
-   [Train in R, run on Android - image segmentation with `torch`](https://blogs.rstudio.com/ai/posts/2021-10-29-segmentation-torch-android/)
    (lvl=3)
-   [Constructing a Chaos Machine](https://urssblogg.netlify.app/post/2020-11-19-synthesizing-temperature-measurements-into-sound/): translating temperature
    measurements into sound in real time ([R notebook](https://gitlab.com/urswilke/chaos_machine_code/-/tree/master/R/preliminary_study/preliminary_study.md)) (lvl=3)


## "Tidyverse" twitter tidbit

> "Evangelist instructors write evangelistic exams."

Comment by [Norman Matloff](#org71ad486) on Twitter about this tweet:

![img](./img/tidyverse.png)

The `data.table` package, which contains the `fread()` function, is
fantastically fast and overall wonderful. `fread()` is featured in
the introductory data import with R course from DataCamp. You
should also take a look at the full `data.table` course - see this
[introductory blog post](https://www.datacamp.com/community/tutorials/data-table-cheat-sheet) for starters ([Willems, 2021](#org3897d29)).


## The battle between Python and R has been concluded

I thought this article with the title from the headline ([Valdeleon,
2021](#orgeac9a36)) is spot on - there's no need to pitch one of these languages
against the other. Each of them has its pros and cons, and it
depends on the job which one you should learn and use.

In fact, many projects require knowledge of both R and Python -
compare the project featured above where temperature measurements
are turned into sound ([Wilke 2021](#org077259e)).


<a id="org45cdd92"></a>

# Good-bye (12-17-2021)

I've just recorded a [short good-bye video](https://youtu.be/IxyqEW9-12s). Here are few parting
notes for this course.

![img](./img/awesome.png)


## What does it all mean?

In a recent critique of the proposed California Mathematics
Framework (CMF), Norman Matloff (known to you as a preeminent
author of books on stats and R, and of the "TidyverseSceptic"
essay), writes ([Matloff, 2021](#orgca5e793)):

> Open-ended data science fits right in to the CMF desire to teach
> kids that "There is no right answer." There is a grain of truth to
> that, but kids must learn how to get the right answer when there is
> one. As one critic rather sarcastically but in my view aptly put
> it, "&#x2026;if you throw a bunch of data at students, they can group
> it, type it into a spreadsheet, plot graphs and so on. It's pretty
> easy to convince yourself they are doing something called 'Data
> Science'. They don't have to do anything particularly useful with
> the data because there are no right answers."

Contrary to this criticism, the point of our course was that there
are "right answers", and though we may have to work hard to get
them, or never succeed, we need to try.

The purpose of the introductory courses on data science is to give
you some of the insights and tools to tackle data to get right
answers and, ideally, solve relevant problems in a scientific
(i.e. systematic, objective, transparent) way.

We've only begun to do this in the first course, and we'll continue
in the "Introduction to Advanced Data Science" (more about that
later).

The course also included a close encounter with agile data science
project management, with the language R, and with the DataCamp
training platform.

With **Scrum**, the best known agile method, you've worked with with
one of the most innovative, fastest growing project management
methods around. Even with yourself as "project owner", Scrum style
might help you complete more of your personal projects successfully
on time.

With **R**, you've had a taste of one of the best data-focused
programming languages, well suited for beginners, powerful from the
first command onwards. There's a lot more music in R, of course,
and no known limitation. Especially, if you're more in love with
data than with coding, you've likely made a friend for life!

The **DataCamp** platform was praised by some in the evaluations - I
still enjoy working with the platform myself, and I will continue
to use it in future courses. Programmed tutorials like these can,
of course, only cover one aspect of learning, and DataCamp does not
replace spending many hours working independently and on your own.

Put all three on your resume right now! What're you waiting for?


## What about the class? Choices and changes.

In the course of the term, you had to endure quite a few changes of
pace and material - it took me a while to adjust to the level and
specific knowledge of the participants.

The good news: you managed - according to your evaluations (thank
you! Almost 60% responded - not quite as much as I had hoped, but
good enough), you learnt something and you thought I was up to the
job!

There are, of course, a million different ways to design such an
introductory class. I made a few choices, including:

1.  Base R (stick shift) instead of "TidyVerse" (automatic)
2.  Use of interactive notebooks (literate programming!)
3.  Use GitHub as a code and materials repository
4.  Create lots of (ungraded) tests
5.  Use of DataCamp assignments
6.  Avoid mathematics as much as possible
7.  Reuse tests for the final exam
8.  Let students pick their own projects

In the next basic data science course (this course will run once a
year, so this will be Fall 2022), I would stick to all of these
choices, except perhaps (6). It would be useful to repeat or
introduce some basic statistics concepts more formally.

I will also make more use of the Schoology gradebook (though the
college might switch to another LMS), and offer more graded
assignments in class.

I will change the DataCamp assignments and let students complete
the "Data Science for Everyone" and "Data Visualization for
Everyone" courses, instead of the more specialized technical
courses. We can learn R and graphic techniques in class.

I did enjoy seeing what you came up with for the final projects. At
the same time (though nobody complained in the evaluation), I think
I overdid it when I asked you to pick your own topic. Instead, I
may eliminate projects from this class, and only do projects in the
followup course when most of the basics are out of the way.


## What next? Follow-up courses.

Here are a few practical suggestions:

-   Use Scrum (= incremental, prototype-oriented, dialog-rich) in
    your projects at school and outside of school
-   Use R regularly for your computational needs
-   Complete the DataCamp courses that you started in this class
-   Get the mobile DataCamp app and do your (daily) drills

Most importantly, don't let existing skills go to waste. If you are
in the followup class, you're okay for another term, but if not,
you may have to make time yourself to keep your skills fresh.

The best if not easiest way to do this is to use these skills,
especially data visualization and rudimentary analysis, in other
courses. Some examples:


## Final words.

Thank you from the bottom of my heart for welcoming me to Lyon by
working with me during this last term. I wish you a Merry
Christmas, a restful break, and I'm looking forward to seeing some
of you again next term!

![img](./img/finals.gif)


<a id="org6e27781"></a>

# References

Really? References in a diary? I know that you know that I am not
enjoying referencing: it's tedious, it slows me down, it's
error-prone etc. But it must be done. If you're not convinced, don't
get a university education, or better, don't work with information
at all, because referencing is about (a) intellectual property
rights (you should care about rights!), and (b) the truth (which
must be spoken!).

<a id="orga201792"></a> Cai Y, Otlu C, Rauenbusch J (28 June 2021). Improve
Visualization of Popular Support for Executive Actions in the
U.S. [Report]. Berlin School of Economics and Law. [Online: GitHub.](https://github.com/birkenkrahe/dsc101/tree/main/projects/examples/cai_et_al_2021)

<a id="org20a4e1b"></a> Cetinkaya-Rundel M (13 Jul 2020). Teaching the Tidyverse
in 2020 - Part 1: Getting started [Blog]. [Online:
education.rstudio.com.](https://education.rstudio.com/blog/2020/07/teaching-the-tidyverse-in-2020-part-1-getting-started/)

<a id="org8b2282c"></a> Cetinkaya-Rundel M (31 Aug 2021). Teaching the Tidyverse
in 2021 [Blog]. [Online: tidyverse.org.](https://www.tidyverse.org/blog/2021/08/teach-tidyverse-2021/)

<a id="org71ad486"></a> Matloff N (2020). TidyverseSceptic - An alternate view
of the Tidyverse "dialect" of the R language, and its promotion by
RStudio. [Online: github.com](https://github.com/matloff/TidyverseSkeptic).

<a id="orgc4a0334"></a> Matloff N (9 Sept 2021). At Crossroads in California
K-12 Math Education [Blog]. [Online: normsaysno.wordpress.com.](https://normsaysno.wordpress.com/2021/09/09/a-crossroads-in-california-k-12-math-education/)

<a id="orgca5e793"></a> Matloff N (2021). The (Academically) Rich Get Richer, the
Poor Get Poorer Tragic Impact on Minority Students of the Proposed
California Math Reform [Blog]. [URL: heather.cs.ucdavis.edu](https://heather.cs.ucdavis.edu/CalMathFrame.html)

<a id="org324eab3"></a> Rauenbusch J (2021). Design in MBA Education in the
U.S. Towards a Design-Integrated Curriculum to Prepare Future
Leaders for a Volatile, Uncertain, Complex, and Ambiguous (VUCA)
World. MA thesis, Berlin School of Economics and Law.

<a id="orgeac9a36"></a> Valdeleon J (29 Aug 2021). The battle between Python & R
has been concluded [blog]. URL: [medium.com](https://medium.com/codex/the-battle-between-python-r-has-been-concluded-b6ffda4ef87).

<a id="org077259e"></a> Wilke U (29 Oct 2021). The Chaos Machine - Synthesizing
Temperature Measurements into Sound [Blog]. URL:
[rssblogg.netlify.app](https://urssblogg.netlify.app/post/2020-11-19-synthesizing-temperature-measurements-into-sound/).

<a id="org3897d29"></a> Willems K (July 14th, 2021). The data.table R Package
Cheat Sheet. URL: [datacamp.com](https://www.datacamp.com/community/tutorials/data-table-cheat-sheet).


# Footnotes

<sup><a id="fn.1" href="#fnr.1">1</a></sup> Huang S/Deng H. Data analytics: a small data approach. CRC Press
(2021).

<sup><a id="fn.2" href="#fnr.2">2</a></sup> How will I know? Because it is clear from the discussion and the
students' response if I presented a figure or an argument that
resonates with them or not. Negative example: my insistence on base R
vs. Tidyverse, or on Open Source vs. commercial software, which I feel
strongly about - but I haven't been able to transfer my sentiments to
students. So perhaps these conflicts have less power than I thought.
