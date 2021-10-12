
# Table of Contents

1.  [What will you learn?](#orga7fe533)
2.  [It's personal](#orgf959421)
3.  [What is markup?](#orge52c8a3)
4.  [What is markdown?](#orgb9ea61b)
    1.  [Why markdown?](#org64e5a52)
    2.  [What is `YAML`](#org0019983)
5.  [What is ORG-MODE?](#org0d68dc1)
6.  [LITERATE PROGRAMMING](#orgcd711ba)
    1.  [Why literate programming?](#org2674bbb)
    2.  [How does literate programming work?](#org050e352)
    3.  [Literate programming workflow](#orgc592f5b)
7.  [Literate programming example](#orgacd18b6)
8.  [LITPROG: PRINTOUT](#org084ffbd)
9.  [LITPROG: STORY](#orgf24b6bd)
10. [LITPROG PROS AND CONS](#org7a55988)
11. [THE CASE FOR LITPROG](#org861c669)
12. [MODERN APPLICATION EXAMPLES](#org72ae508)
13. [AGILE METHODOLOGIES](#org7efabde)
14. [NOTEBOOK EXAMPLES](#org7f963f6)
15. [NOTEBOOK TUTORIALS](#org1f1a5ea)
16. [ORG-MODE AGAIN](#org47a5e1e)
17. [NOTEBOOK DEMO (RSTUDIO CLOUD)](#org1af84cf)
18. [NOTEBOOK APPLICATIONS FOR YOU](#orgb03995c)
19. [REFERENCES](#org5347bf8)



<a id="orga7fe533"></a>

# What will you learn?

-   What is the main idea behind the Web?
-   What are Markup and Markdown?
-   What is "literate programming"?
-   What does it have to do with data science notebooks?
-   Which data science notebooks are out there?
-   How can I use notebooks for data science?
-   How can I use notebooks in my own work?

![img](./img/backflip.jpg)


<a id="orgf959421"></a>

# It's personal

-   DESY Particle Physics PhD
-   CERN WWW development
-   What is the main idea behind the Web?

![img](./img/desy.png)

*Image: glimpse of the early days of the web*


<a id="orge52c8a3"></a>

# What is markup?

-   HTML = HyperText Markup Language
-   Hide meta information - unlike "WYSIWIG"
-   Example - active text element behind [This is a link](https://www.w3schools.com).
    
    Right-click and choose `Inspect` to see the active element:
    
    ![img](./img/html.png)

Q: *Who can write HTML (and CSS) documents?*<sup><a id="fnr.1" class="footref" href="#fn.1">1</a></sup>


<a id="orgb9ea61b"></a>

# What is markdown?

> 
> 
> »The idea for Markdown is to make it easy to read, write, and edit
> prose. HTML is a publishing format; Markdown is a writing
> format. Thus, Markdown’s formatting syntax only addresses issues that
> can be conveyed in plain text.« &#x2013; [John Gruber](#orgb96c5a7)


<a id="org64e5a52"></a>

## Why markdown?

-   Easy-to-read and easy-to-write
-   Easy to customize
-   Even easier than HTML:

![img](./img/md.png)

*Q: Have you come across Markup or Markdown?*


<a id="org0019983"></a>

## What is `YAML`

-   [YAML](https://en.wikipedia.org/wiki/YAML) ("YAML Ain't Markup Language")
-   Used for configuration (e.g. headers)
-   Used in R Markdown Notebooks

![img](./img/yaml.png)


<a id="org0d68dc1"></a>

# What is [ORG-MODE](https://orgmode.org/)?

-   Major GNU Emacs editor mode<sup><a id="fnr.2" class="footref" href="#fn.2">2</a></sup>
-   Plain text markup + export + publishing
-   Literate Programming environment<sup><a id="fnr.3" class="footref" href="#fn.3">3</a></sup>

*Q: Can you think of any reasons to live life in plain text?*

![img](./img/org.png)

*Image: this very page in Emacs Org-mode.*


<a id="orgcd711ba"></a>

# LITERATE PROGRAMMING

> »Instead of imagining that our main task is to instruct a *computer*
> what to do, let us concentrate rather on explaining to *human beings*
> what we want a computer to do.« &#x2013; [Donald Knuth](#orgc7d07ec)

![img](./img/knuth.jpg)


<a id="org2674bbb"></a>

## Why literate programming?

-   Machines cannot handle uncertainty
-   Humans like stories

![img](./img/neumann.png)


<a id="org050e352"></a>

## How does literate programming work?

-   Write programs for use by humans *and* by machines
-   Write mainly documentation that also contains code

![img](./img/scoring.png)


<a id="orgc592f5b"></a>

## Literate programming workflow

-   Documentation + code is contained in one file (`file.w`)
-   Tangling leads to a file that the computer can run
-   Weaving leads to a file that can be printed

![img](./img/cweb.png)


<a id="orgacd18b6"></a>

# Literate programming example

-   [`advent`](https://en.wikipedia.org/wiki/Colossal_Cave_Adventure) is the first digital Role Playing Game (RPG)
-   It was rewritten in `cweb` by Don Knuth
-   *Try typing `advent` in your terminal!*

![img](./img/advent.png)


<a id="org084ffbd"></a>

# LITPROG: PRINTOUT

 Figure [54](#orgfda1399) shows the printout that corresponds to figure
]] ([source](http://literateprogramming.com/adventure.pdf)).

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/define.png "Screenshot of Knuth's `cweb` version of `advent`.")


<a id="orgf24b6bd"></a>

# LITPROG: STORY

-   Automatic index of commands, variables, objects
-   Index of subroutines, table of contents
-   Support for digital, code-based storytelling

---

Figures [59](#org4217252) and [60](#orgf6980b1) show part of the index and the table
of contents of the `cweb` printout.

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/index.png "Index for the "Adventure" game by (Crowther, 1975), [Knuth (1998)](#org458d71c).")

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/toc.png "Table of Contents for the "Adventure" game (Crowther, 1975), [Knuth (1998)](#org458d71c).")


<a id="org7a55988"></a>

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


<a id="org861c669"></a>

# THE CASE FOR LITPROG

-   Code and documentation in separate files and rarely synchronized,
-   Variable names that are mnemonics and acronyms, not words,
-   Documentation that is seldom created by the programmer, and
-   Documentation that has a lower priority than the program.

See also: [Childs, 2010](#orge09c97d):

> »It is commonly accepted in software engineering circles that one of
> the greatest needs in computing is the reduction of the cost of
> maintenance of codes.  Maintenance programmers spend at least half of
> their time trying to understand what code does and maintenance is
> accepted to be 60% to 80% of a code’s cost.«


<a id="org72ae508"></a>

# MODERN APPLICATION EXAMPLES

-   [Extreme Programming](http://www.extremeprogramming.org/) (XP)
-   [Agile Modeling](http://agilemodeling.com/) (AM)
-   Interactive programming (see figure [71](#org7b8a8a7))

---

Figure [71](#org7b8a8a7) shows a computational [IPython](http://ipython.org/) notebook
from 2005. IPython is the precursor of Jupyter notebooks.

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/ipython.png "IPython notebook. By Shishirdasika, [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0), via Wikimedia Commons")


<a id="org7efabde"></a>

# AGILE METHODOLOGIES

-   Ways to develop and document anything
-   Better suited for *complex* projects and *culturally* diverse teams
-   Core value: optimize customer *communication*

---

Figure [76](#orgf5ab39b): [Scrum](https://www.scrum.org/resources/what-is-scrum/) is the best known agile methodology.

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/scrum.png "Scrum values (Source: scrum.org)")


<a id="org7f963f6"></a>

# NOTEBOOK EXAMPLES

-   [Subsetting quiz as shiny app with `learnr` package](https://monty.shinyapps.io/subsetting/#section-introduction)
-   [GNA Internet Course on Literate Programming (1994)](https://web.archive.org/web/20161002004240/http://www.desy.de/user/projects/LitProg/Course.html)
-   [SQL cells in Deepnote (demo, 1 min)](https://docs.deepnote.com/deepnote-crash-course-videos)
-   [Kaggle notebook from Pima Indians database](https://www.kaggle.com/uciml/pima-indians-diabetes-database)
-   [Count cloud notebook](https://count.co/n/S9PSxqZBPM9)
-   [Introduction to DataCamp projects (with R)](https://projects.datacamp.com/projects/41)
-   [R Markdown Outputs Gallery](https://rmarkdown.rstudio.com/gallery.html)


<a id="org1f1a5ea"></a>

# NOTEBOOK TUTORIALS

-   Tutorial: [Jupyter and R Markdown: Notebooks with R](https://www.datacamp.com/community/blog/jupyter-notebook-r) (2016)
-   Book: [R notebook (bookdown)](https://bookdown.org/yihui/rmarkdown/notebook.html)
-   Article: [R notebooks for dummies](https://medium.com/swlh/r-notebook-for-dummies-save-and-share-results-easily-51d343a4882) (2020)
-   Course: [Reporting with R Markdown](https://learn.datacamp.com/courses/reporting-with-rmarkdown) (2020)
-   Course: [R Markdown from RStudio](https://rmarkdown.rstudio.com/index.html)


<a id="org47a5e1e"></a>

# ORG-MODE AGAIN

-   Notebooks work with R, SQL, Python,&#x2026;anything
-   [SQLite](https://sqlite.org/about.html) example (SQLite = SQL for IoT)
-   Present, too, if you like
-   R notebook example (print+plot)

---

Figure [94](#org8848acb) shows an SQLite notebook example

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/sqlite.png "SQLite notebook example (Emacs/Org-mode)")


<a id="org1af84cf"></a>

# NOTEBOOK DEMO (RSTUDIO CLOUD)

-   EDA using the [`Pima` Indian data set](http://heather.cs.ucdavis.edu/FasteR/data/Pima.csv) (via Matloff)
-   Head over to [this RStudio cloud notebook](https://rstudio.cloud/project/2030701) to start
-   Compare your results with [this solution (PDF)](https://moodle.hwr-berlin.de/mod/resource/view.php?id=911275)

---

Figure [99](#orgfbdd915) shows a screenshot from the RStudio cloud workspace
where we will practice R notebook creation and execution.

---

![img](c:/Users/birkenkrahe/OneDrive/2020_Winter/DS101/ds_lectures/6_litpRog/img/demo.png "RStudio cloud workspace with R notebook demo.")


<a id="orgb03995c"></a>

# NOTEBOOK APPLICATIONS FOR YOU

-   Emacs + ESS + Org-mode (Tutorial)
-   RStudio notebooks
-   Write your next paper or thesis as a "literate program"<sup><a id="fnr.4" class="footref" href="#fn.4">4</a></sup>


<a id="org5347bf8"></a>

# REFERENCES

(1) <a id="orgc7d07ec"></a> Donald E. Knuth, "Von Neumann's First Computer
Program". Computing Surveys, 2(4), 1970.

(2) <a id="orgb96c5a7"></a> John Gruber, "Markdown:
Syntax". Blog. [daringfireball.net](https://daringfireball.net/projects/markdown/syntax#block)

(3) <a id="orgde4f843"></a> Donald E. Knuth and Silvio Levy, "The `CWEB` System of
Structured Documentation", 2002. Manual. [literateprogramming.com](http://www.literateprogramming.com/cweb.pdf)

(4) <a id="org458d71c"></a> [Don Woods and Don Knuth, 1998.](http://www.literateprogramming.com/adventure.pdf)

(5) <a id="org1886ba9"></a> Bart Childs, "Literate Programming, Why?"
(n.d.). [literateprogramming.com](http://www.literateprogramming.com/bchilds1.pdf)

(6) <a id="orge09c97d"></a> Bart Childs, "Thirty years of literate
programming and more?". [TUGboat, Volume 31(2), 2010:183-188](https://www.tug.org/TUGboat/tb31-2/tb98childs.pdf).

(7) <a id="orgba1d261"></a> Zachary M. Smith, "R Markdown Crash Course",
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
