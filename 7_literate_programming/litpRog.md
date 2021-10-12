
# Table of Contents

1.  [WHAT WILL YOU LEARN?](#org930a8c8)
2.  [IT'S PERSONAL](#orgc7744d0)
3.  [WHAT IS MARKUP?](#org85181fe)
4.  [WHAT IS MARKDOWN? (1)](#org60ca81c)
5.  [WHAT IS MARKDOWN? (2)](#orgc212ac8)
6.  [WHAT IS MARKDOWN (3)](#org55e9332)
7.  [ORG-MODE](#org9c3e4e9)
8.  [LITERATE PROGRAMMING](#orgd840630)
9.  [LITPROG: WHY?](#orgf788ee1)
10. [LITPROG: HOW?](#org16d5390)
11. [LITPROG: WORKFLOW](#orgd42921a)
12. [LITPROG: EXAMPLE](#org90b40cb)
13. [LITPROG: PRINTOUT](#org3333af6)
14. [LITPROG: STORY](#org90ee213)
15. [LITPROG PROS AND CONS](#org199c77a)
16. [THE CASE FOR LITPROG](#orgef69a8c)
17. [MODERN APPLICATION EXAMPLES](#org2839fe8)
18. [AGILE METHODOLOGIES](#org137cd0b)
19. [NOTEBOOK EXAMPLES](#orgfb0dccf)
20. [NOTEBOOK TUTORIALS](#org6ea64ec)
21. [ORG-MODE AGAIN](#org91b9198)
22. [NOTEBOOK DEMO (RSTUDIO CLOUD)](#orgb8200aa)
23. [NOTEBOOK APPLICATIONS FOR YOU](#org9be2069)
24. [REFERENCES](#org4addd77)

<style>
blockquote {
    margin-bottom: 10px;
    padding: 10px;
    background-color: #FFF8DC;
    border-left: 2px solid #ffeb8e;
    border-left-color: rgb(255, 228, 102);
    display: block;
    margin-block-start: 1em;
    margin-block-end: 1em;
    margin-inline-start: 40px;
    margin-inline-end: 40px;
}
pre {
    margin-bottom: 10px;
    padding: 10px;
    background-color: black;
    color: white;
    border-left: 2px solid #ffeb8e;
    border-left-color: red;
    display: block;
    margin-block-start: 1em;
    margin-block-end: 1em;
    margin-inline-start: 40px;
    margin-inline-end: 40px;
}
img {
  border: 1px solid #2F4F4F;
}
ul {
    margin-bottom: 10px;
    padding: 10px;
    background-color: #FAEBD7;
    color: black;
    border-left: 2px solid #ffeb8e;
    border-left-color: black;
    display: block;
    margin-block-start: 4em;
    margin-block-end: 1em;
    margin-inline-start: 40px;
    margin-inline-end: 40px;
    list-style-type: circle ;
    list-style-position: inside;
}
 </style>


<a id="org930a8c8"></a>

# WHAT WILL YOU LEARN?

-   What is the main idea behind the Web?
-   What are Markup and Markdown?
-   What is "literate programming"?
-   What does it have to do with data science notebooks?
-   Which data science notebooks are out there?
-   How can I use notebooks for data science?
-   How can I use notebooks in my own work?

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/img/moodle-pics/r_notebooks.jpg "Photo: Peggy Bacon in mid-air backflip, Sydney 1937. Source: [State Lib. NSW@flickr](https://flic.kr/p/5FytjL)")


<a id="orgc7744d0"></a>

# IT'S PERSONAL

-   DESY Particle Physics PhD
-   CERN WWW development
-   What is the main idea behind the Web?

---

*See figure [13](#orgc33e152) for a glimpse of the early days of the Web.*

---

![img](./img/desy.png "Virtual Library page for Literate Programming @DESY, 1994 (Source: Wayback Machine)")


<a id="org85181fe"></a>

# WHAT IS MARKUP?

-   HTML = HyperText Markup Language
-   Hide meta information - unlike "WYSIWIG"
-   Example - active text element behind [This is a link](https://www.w3schools.com).

    <a href="https://www.w3schools.com">This is a link</a>

Q: *Who can write HTML (and CSS) documents?*<sup><a id="fnr.1" class="footref" href="#fn.1">1</a></sup> 


<a id="org60ca81c"></a>

# WHAT IS MARKDOWN? (1)

> »The idea for Markdown is to make it easy to read, write, and edit
> prose. HTML is a publishing format; Markdown is a writing
> format. Thus, Markdown’s formatting syntax only addresses issues
> that can be conveyed in plain text.« &#x2013; [John Gruber](#orgcf40cf9)


<a id="orgc212ac8"></a>

# WHAT IS MARKDOWN? (2)

-   Easy-to-read and easy-to-write
-   Easy to customize (see figure [26](#org26e2439))
-   Even easier than HTML:

    [This is a link](https://www.w3schools.com)
    
    <a href="https://www.w3schools.com">This is a link</a>

*Q: Have you come across Markup or Markdown?*


<a id="org55e9332"></a>

# WHAT IS MARKDOWN (3)

-   [YAML](https://en.wikipedia.org/wiki/YAML) ("YAML Ain't Markup Language")
-   Used for configuration (e.g. headers)
-   Used in R Markdown Notebooks

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/yaml.png "YAML header in R Markdown file (left) and rendering (right) (Source: [Smith 2020](#org64ea003))")


<a id="org9c3e4e9"></a>

# [ORG-MODE](https://orgmode.org/)

-   Major GNU Emacs editor mode<sup><a id="fnr.2" class="footref" href="#fn.2">2</a></sup>
-   Plain text markup + export + publishing
-   Literate Programming environment<sup><a id="fnr.3" class="footref" href="#fn.3">3</a></sup>

*Q: Can you think of any reasons to live life in plain text?*

---

See figure [32](#orgcc3b7e9) for an example of this very page displayed in
Emacs Org-mode.

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/org.png "GNU Emacs Org-mode Markup example")


<a id="orgd840630"></a>

# LITERATE PROGRAMMING

> »Instead of imagining that our main task is to instruct a *computer*
> what to do, let us concentrate rather on explaining to *human beings*
> what we want a computer to do.« &#x2013; [Donald Knuth](#org68bb2b1)

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/knuth.jpg "Donald M. Knutz, 1958, working on an IBM 650 computer ([Source](https://catonmat.net/donald-knuths-first-computer)).")


<a id="orgf788ee1"></a>

# LITPROG: WHY?

-   Machines cannot handle uncertainty (figure [37](#org2424872))
-   Humans like stories

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/neumann.png "Von Neumann's First Computer Program ([Knuth, 1970](#org68bb2b1))")


<a id="org16d5390"></a>

# LITPROG: HOW?

-   Write programs for use by humans *and* by machines
-   Write mainly documentation that also contains code

---

Figure [41](#org8df8ea9) shows part of a literate program.
program

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/scoring.png "Another screenshot of Knuth's `cweb` version of `advent`.")


<a id="orgd42921a"></a>

# LITPROG: WORKFLOW

-   Documentation + code is contained in one file (`file.w`)
-   Tangling leads to a file that the computer can run
-   Weaving leads to a file that can be printed

---

See figure [46](#org2b6d0e6) for the complete workflow.

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/cweb.png "Literate programming process chain ([Knuth/Levy, 2002](#org943a870)).")


<a id="org90b40cb"></a>

# LITPROG: EXAMPLE

-   [`advent`](https://en.wikipedia.org/wiki/Colossal_Cave_Adventure) is the first digital Role Playing Game (RPG)
-   It was rewritten in `cweb` by Don Knuth (see figure [58](#orgb99901e))
-   *Try typing `advent` in your terminal!*

---

Figure [51](#orgae888b7) shows the first few moments of the game ([source](http://literateprogramming.com/adventure.pdf)).

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/advent.png "Adventure game in Linux - see `advent(6)`")


<a id="org3333af6"></a>

# LITPROG: PRINTOUT

Figure [53](#org7c2970e) shows the printout that corresponds to figure
[51](#orgae888b7) ([source](http://literateprogramming.com/adventure.pdf)).

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/define.png "Screenshot of Knuth's `cweb` version of `advent`.")


<a id="org90ee213"></a>

# LITPROG: STORY

-   Automatic index of commands, variables, objects
-   Index of subroutines, table of contents
-   Support for digital, code-based storytelling

---

Figures [58](#orgb99901e) and [59](#orgb72c111) show part of the index and the table
of contents of the `cweb` printout. 

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/index.png "Index for the "Adventure" game by (Crowther, 1975), [Knuth (1998)](#org3678a3f).")

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/toc.png "Table of Contents for the "Adventure" game (Crowther, 1975), [Knuth (1998)](#org3678a3f).")


<a id="org199c77a"></a>

# LITPROG PROS AND CONS

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left"><b>LITPROG PROS</b></th>
<th scope="col" class="org-left"><b>LITPROG *CONS</b></th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">Storytelling supported</td>
<td class="org-left">Requires thought</td>
</tr>
</tbody>

<tbody>
<tr>
<td class="org-left">Prettyprinting w/\(\TeX\)</td>
<td class="org-left">\(\TeX\) difficult to learn</td>
</tr>
</tbody>

<tbody>
<tr>
<td class="org-left">Automatic index/TOC</td>
<td class="org-left">Requires (different) training</td>
</tr>
</tbody>

<tbody>
<tr>
<td class="org-left">Free Software</td>
<td class="org-left">Standardisation difficult</td>
</tr>
</tbody>
</table>


<a id="orgef69a8c"></a>

# THE CASE FOR LITPROG

-   Code and documentation in separate files and rarely synchronized,
-   Variable names that are mnemonics and acronyms, not words,
-   Documentation that is seldom created by the programmer, and
-   Documentation that has a lower priority than the program.

See also: [Childs, 2010](#orgf9bc2ec):

> »It is commonly accepted in software engineering circles that one of
> the greatest needs in computing is the reduction of the cost of
> maintenance of codes.  Maintenance programmers spend at least half of
> their time trying to understand what code does and maintenance is
> accepted to be 60% to 80% of a code’s cost.«


<a id="org2839fe8"></a>

# MODERN APPLICATION EXAMPLES

-   [Extreme Programming](http://www.extremeprogramming.org/) (XP)
-   [Agile Modeling](http://agilemodeling.com/) (AM)
-   Interactive programming (see figure [70](#orgc142d36))

---

Figure [70](#orgc142d36) shows a computational [IPython](http://ipython.org/) notebook
from 2005. IPython is the precursor of Jupyter notebooks.

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/ipython.png "IPython notebook. By Shishirdasika, [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0), via Wikimedia Commons")


<a id="org137cd0b"></a>

# AGILE METHODOLOGIES

-   Ways to develop and document anything
-   Better suited for *complex* projects and *culturally* diverse teams
-   Core value: optimize customer *communication*

---

Figure [75](#orgbcf92f1): [Scrum](https://www.scrum.org/resources/what-is-scrum/) is the best known agile methodology.

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/scrum.png "Scrum values (Source: scrum.org)")


<a id="orgfb0dccf"></a>

# NOTEBOOK EXAMPLES

-   [Subsetting quiz as shiny app with `learnr` package](https://monty.shinyapps.io/subsetting/#section-introduction)
-   [GNA Internet Course on Literate Programming (1994)](https://web.archive.org/web/20161002004240/http://www.desy.de/user/projects/LitProg/Course.html)
-   [SQL cells in Deepnote (demo, 1 min)](https://docs.deepnote.com/deepnote-crash-course-videos)
-   [Kaggle notebook from Pima Indians database](https://www.kaggle.com/uciml/pima-indians-diabetes-database)
-   [Count cloud notebook](https://count.co/n/S9PSxqZBPM9)
-   [Introduction to DataCamp projects (with R)](https://projects.datacamp.com/projects/41)
-   [R Markdown Outputs Gallery](https://rmarkdown.rstudio.com/gallery.html)


<a id="org6ea64ec"></a>

# NOTEBOOK TUTORIALS

-   Tutorial: [Jupyter and R Markdown: Notebooks with R](https://www.datacamp.com/community/blog/jupyter-notebook-r) (2016)
-   Book: [R notebook (bookdown)](https://bookdown.org/yihui/rmarkdown/notebook.html)
-   Article: [R notebooks for dummies](https://medium.com/swlh/r-notebook-for-dummies-save-and-share-results-easily-51d343a4882) (2020)
-   Course: [Reporting with R Markdown](https://learn.datacamp.com/courses/reporting-with-rmarkdown) (2020)
-   Course: [R Markdown from RStudio](https://rmarkdown.rstudio.com/index.html)


<a id="org91b9198"></a>

# ORG-MODE AGAIN

-   Notebooks work with R, SQL, Python,&#x2026;anything
-   [SQLite](https://sqlite.org/about.html) example (SQLite = SQL for IoT)
-   Present, too, if you like
-   R notebook example (print+plot)

---

Figure [93](#orgbb56561) shows an SQLite notebook example

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/sqlite.png "SQLite notebook example (Emacs/Org-mode)")


<a id="orgb8200aa"></a>

# NOTEBOOK DEMO (RSTUDIO CLOUD)

-   EDA using the [`Pima` Indian data set](http://heather.cs.ucdavis.edu/FasteR/data/Pima.csv) (via Matloff)
-   Head over to [this RStudio cloud notebook](https://rstudio.cloud/project/2030701) to start
-   Compare your results with [this solution (PDF)](https://moodle.hwr-berlin.de/mod/resource/view.php?id=911275)

---

Figure [98](#orga60bbcb) shows a screenshot from the RStudio cloud workspace
where we will practice R notebook creation and execution.

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/demo.png "RStudio cloud workspace with R notebook demo.")


<a id="org9be2069"></a>

# NOTEBOOK APPLICATIONS FOR YOU

-   Emacs + ESS + Org-mode (Tutorial)
-   RStudio notebooks
-   Write your next paper or thesis as a "literate program"<sup><a id="fnr.4" class="footref" href="#fn.4">4</a></sup>


<a id="org4addd77"></a>

# REFERENCES

(1) <a id="org68bb2b1"></a> Donald E. Knuth, "Von Neumann's First Computer
Program". Computing Surveys, 2(4), 1970.

(2) <a id="orgcf40cf9"></a> John Gruber, "Markdown:
Syntax". Blog. [daringfireball.net](https://daringfireball.net/projects/markdown/syntax#block)

(3) <a id="org943a870"></a> Donald E. Knuth and Silvio Levy, "The `CWEB` System of
Structured Documentation", 2002. Manual. [literateprogramming.com](http://www.literateprogramming.com/cweb.pdf)

(4) <a id="org3678a3f"></a> [Don Woods and Don Knuth, 1998.](http://www.literateprogramming.com/adventure.pdf)

(5) <a id="org0fe31c5"></a> Bart Childs, "Literate Programming, Why?"
(n.d.). [literateprogramming.com](http://www.literateprogramming.com/bchilds1.pdf)

(6) <a id="orgf9bc2ec"></a> Bart Childs, "Thirty years of literate
programming and more?". [TUGboat, Volume 31(2), 2010:183-188](https://www.tug.org/TUGboat/tb31-2/tb98childs.pdf).

(7) <a id="org64ea003"></a> Zachary M. Smith, "R Markdown Crash Course",
2020-03-02. [github.com](https://zsmith27.github.io/rmarkdown_crash-course/index.html)


# Footnotes

<sup><a id="fn.1" href="#fnr.1">1</a></sup> For a live view, right click & pick "View page source" in your
browser.

<sup><a id="fn.2" href="#fnr.2">2</a></sup> A major mode in Emacs is an editing environment that is
customized for a particular purpose - e.g. coding in a specific
language like R, or writing notes, like Org-mode, or presenting, like
Org-present. Most editors don't have this possibility. For GNU Emacs,
all modes are easily extensible, that is users can create their own
customizations and contribute them to the editor - just like packages
in R.

<sup><a id="fn.3" href="#fnr.3">3</a></sup> See also: [Org-mode spreadsheets (Gif)](https://orgmode.org/resources/img/features/tables.gif)

<sup><a id="fn.4" href="#fnr.4">4</a></sup> Remember: litprog means "documentation first" - this is
data-driven storytelling from the story rather than from the data
end - much easier and much more likely to result in a good story!
