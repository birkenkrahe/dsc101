
# Table of Contents

1.  [What is this?](#org79dc3ee)
2.  [Redrawing Google trend chart (07-13-2021)](#org017e9c5)
3.  [Data science process (07-15-2021)](#org98c17f2)
4.  ["Teaching the tidyverse in 2021" (09-07-2021)](#org6baeb7c)
5.  [References](#orgfa67bfc)



<a id="org79dc3ee"></a>

# What is this?

A place for irregular articles of possible interest to students of
the DSC 101 course, mostly to avoid lengthy emails and to park
content that I may want to develop later on time permitting.


<a id="org017e9c5"></a>

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
<td class="org-left">`read.table`</td>
<td class="org-left">upload data as `data.frame`</td>
</tr>


<tr>
<td class="org-left">`library()`</td>
<td class="org-left">load R package</td>
</tr>


<tr>
<td class="org-left">`anytime::anydate()`</td>
<td class="org-left">convert vector to `Date` format</td>
</tr>


<tr>
<td class="org-left">`cbind()`</td>
<td class="org-left">attach column to `data.frame`</td>
</tr>


<tr>
<td class="org-left">`$`</td>
<td class="org-left">extract vector from `data.frame`</td>
</tr>


<tr>
<td class="org-left">`<-`</td>
<td class="org-left">assign right hand to left hand side</td>
</tr>


<tr>
<td class="org-left">`plot()`</td>
<td class="org-left">draw scatter plot</td>
</tr>


<tr>
<td class="org-left">`lines()`</td>
<td class="org-left">draw line graph</td>
</tr>


<tr>
<td class="org-left">`barplot()`</td>
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


<a id="org98c17f2"></a>

# Data science process (07-15-2021)

I was digging around my notes made for an online test lecture on May
19, on "Exploring data with R" (see [presentation](https://github.com/birkenkrahe/dsc101/blob/main/wiki/talk_presentation.pdf) & [notes](https://github.com/birkenkrahe/dsc101/blob/main/wiki/talk_notes.pdf)), for an
update on a [data science overview lecture](https://github.com/birkenkrahe/dsc101/tree/main/2_datascience). For this talk, I had
developed the model shown in figure [11](#orgaf8bfd2): there are two pathways
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
clients (see figure [14](#org7eed7ce)).

![img](https://github.com/birkenkrahe/dsc101/blob/main/img/righteda.png)

I added this to the other two data science workflow images that I
already had in the lecture. And I added yet another one (see figure
[16](#org35bc779)), from a recent book on data analytics<sup><a id="fnr.1" class="footref" href="#fn.1">1</a></sup>. I really like
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


<a id="org6baeb7c"></a>

# "Teaching the tidyverse in 2021" (09-07-2021)

I've mentioned the "tidyverse" before. This morning, I read an
article (posted in RWeekly, the weekly aggregator of R news that you
should subscribe to) "Teaching the tidyverse in 2021"
([Cetinkaya-Rundel, 2021](#orgf9596b5)), which upset me. I will briefly explain
why. The article mentions the 2020 series of the same title, which
begins with the claim that "updates to tidyverse packages are
specifically designed to make it easier for new learners to get
started with doing data science in R." ([Cetinkaya-Rundel, 2020](#orgde70356)).

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


<a id="orgfa67bfc"></a>

# References

Really? References in a diary? I know that you know that I am not
enjoying referencing: it's tedious, it slows me down, it's
error-prone etc. But it must be done. If you're not convinced, don't
get a university education, or better, don't work with information
at all, because referencing is about (a) intellectual property
rights (you should care about rights!), and (b) the truth (which
must be spoken!).

<a id="orgde70356"></a> Cetinkaya-Rundel M (13 Jul 2020). Teaching the Tidyverse
in 2020 - Part 1: Getting started [Blog]. [Online:
education.rstudio.com.](https://education.rstudio.com/blog/2020/07/teaching-the-tidyverse-in-2020-part-1-getting-started/)

<a id="orgf9596b5"></a> Cetinkaya-Rundel M (31 Aug 2021). Teaching the Tidyverse
in 2021 [Blog]. [Online: tidyverse.org.](https://www.tidyverse.org/blog/2021/08/teach-tidyverse-2021/)

<a id="orgfa96f5c"></a> Matloff N (2020). TidyverseSceptic - An alternate view
of the Tidyverse "dialect" of the R language, and its promotion by
RStudio. [Online: github.com](https://github.com/matloff/TidyverseSkeptic). 


# Footnotes

<sup><a id="fn.1" href="#fnr.1">1</a></sup> Huang S/Deng H. Data analytics: a small data approach. CRC Press
(2021).

<sup><a id="fn.2" href="#fnr.2">2</a></sup> How will I know? Because it is clear from the discussion and the
students' response if I presented a figure or an argument that
resonates with them or not. Negative example: my insistence on base R
vs. Tidyverse, or on Open Source vs. commercial software, which I feel
strongly about - but I haven't been able to transfer my sentiments to
students. So perhaps these conflicts have less power than I thought.
