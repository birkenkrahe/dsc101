
# Table of Contents

-   [Preface](#orga7442cd)
    -   [Key points](#org6864a0e)
    -   [Structure](#org481a63f)
    -   [Concept summary](#org439b43f)
        -   [](#org469b9c9)
        -   [](#org11a4bef)
    -   [Challenges <code>[2/2]</code>](#org22ab656)
-   [Getting started](#org9986139)
    -   [Video series: Introduction to R (03/2021)](#org979ac71)
    -   [Code summary](#org4f5312e)
    -   [Concept summary](#orgb512199)
    -   [Challenges <code>[5/5]</code>](#org2e9ae85)



<a id="orga7442cd"></a>

# Preface


<a id="org6864a0e"></a>

## Key points

-   Fast route to data science
-   Written for Non-programmers
-   Uses real problems and real data
-   Focus on shell rather than IDE
-   Focus on base R
-   Create your own exercises


<a id="org481a63f"></a>

## Structure

![img](./img/fasteR.png)

<div class="notes">
1.  **Introduction to R** - installation, data structures and
    simple exploratory data analysis (EDA)
2.  **Writing functions** - creating own structures and routines
3.  **Data Visualization** - types of plots and graphics
4.  **Regression in R** - predictive statistical inference
5.  **Text mining in R** - exploring textual documents
6.  **Coding & Modeling** - utilities, styles, functional and OOP

7.  Combine with DataCamp practice and additional exercises
8.  Check additional textbooks to go deeper or branch out

</div>


<a id="org439b43f"></a>

## Concept summary


<a id="org469b9c9"></a>

### 

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">**Concept**</th>
<th scope="col" class="org-left">**Definition**</th>
<th scope="col" class="org-left">**Example/Reference**</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">IDE</td>
<td class="org-left">Integrated Development Environment</td>
<td class="org-left">[RStudio](https://rstudio.com)</td>
</tr>


<tr>
<td class="org-left">[Shell](https://en.wikipedia.org/wiki/Shell_%28computing%29)</td>
<td class="org-left">Service program or console or CLI</td>
<td class="org-left">R shell, [bash](https://www.gnu.org/software/bash/)</td>
</tr>


<tr>
<td class="org-left">Base R</td>
<td class="org-left">Basic R package (not "Tidyverse")<sup><a id="fnr.1" class="footref" href="#fn.1">1</a></sup></td>
<td class="org-left">[`dplyr` vs. base R](https://cran.r-project.org/web/packages/dplyr/vignettes/base.html)</td>
</tr>
</tbody>
</table>


<a id="org11a4bef"></a>

### 

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">**Concept**</th>
<th scope="col" class="org-left">**Definition**</th>
<th scope="col" class="org-left">**Example/Reference**</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">OOP</td>
<td class="org-left">Object-oriented programming</td>
<td class="org-left">[C++](https://www.stroustrup.com/C++.html)<sup><a id="fnr.2" class="footref" href="#fn.2">2</a></sup></td>
</tr>


<tr>
<td class="org-left">EDA</td>
<td class="org-left">Exploratory Data Analysis</td>
<td class="org-left">[Data Vis 4 Everyone](https://learn.datacamp.com/courses/data-visualization-for-everyone)<sup><a id="fnr.3" class="footref" href="#fn.3">3</a></sup></td>
</tr>


<tr>
<td class="org-left">Function</td>
<td class="org-left">Takes input, returns output</td>
<td class="org-left">`"Hello, world"`<sup><a id="fnr.4" class="footref" href="#fn.4">4</a></sup></td>
</tr>
</tbody>
</table>


<a id="org22ab656"></a>

## Challenges <code>[2/2]</code>

1.  [X] How would you describe the differences in installing R on
    different operating system to someone, who only uses computers?
2.  [X] Which (online) tutorials do you like, which ones did you
    finish, and what did you like about these tutorials?

<div class="notes">
1.  Same (mirror) site for download; different: files, installation
    process; opening the program. Expansion: write your own tutorial
    installation notes for users of Linux, Windows, MacOS. Here is
    an [example from DataCamp](https://www.datacamp.com/community/tutorials/installing-R-windows-mac-ubuntu).
2.  I really like tutorials to refresh my memory. One that I really
    liked was Derek Banas' "[SQLite3 Tutorial](https://youtu.be/QjICgmk31js)" on YouTube. I liked
    the amount of information, the flow, the speed, the cheat
    sheet - and I subsequently copied this style for many of my own
    tutorial sessions.

</div>


<a id="org9986139"></a>

# Getting started

-   Install R from the [R Project Site](https://r-project.org)
-   Start up the R console
-   End session by typing `q()`
-   Do not "save workspace image" (type `n`)


<a id="org979ac71"></a>

## [Video series: Introduction to R (03/2021)](https://youtube.com/playlist?list=PL6SfZh1-kWXkLa45V6JeEhNZEXvsmUR1f)

In this video series (recorded in March 2021 for a course of
students in a Master program of internatinal business) I start R
for the first time and go through the basics of opening, closing
the program, getting help, getting around and installing additional
programs.

Total playing time ca. 50 minutes (quite a lot of chit-chat)

![img](./img/opening_R.png)

1.  Installation and shell
2.  Opening R for the first time
3.  Getting help
4.  R working environment
5.  Installing and loading R packages


<a id="org4f5312e"></a>

## Code summary

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">**Command**</th>
<th scope="col" class="org-left">**Description**</th>
<th scope="col" class="org-left">**Example/Ref**</th>
<th scope="col" class="org-left">&#xa0;</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">`sudo`</td>
<td class="org-left">Super-user program</td>
<td class="org-left">`sudo apt update`<sup><a id="fnr.5" class="footref" href="#fn.5">5</a></sup></td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">`license()`</td>
<td class="org-left">Distribution details</td>
<td class="org-left">[GNU Public General License](https://www.gnu.org/licenses/gpl-3.0.en.html)</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">`citation()`</td>
<td class="org-left">How to cite the R project</td>
<td class="org-left">[Citation examples](https://www.programmingr.com/examples/neat-tricks/r-citation/)</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">`help()`</td>
<td class="org-left">Invoking the man pages</td>
<td class="org-left">`help(help)`</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">`demo()`</td>
<td class="org-left">Demonstrations</td>
<td class="org-left">`demo(graphics)`</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">`example()`</td>
<td class="org-left">Illustrated examples</td>
<td class="org-left">`example(mean)`</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">`?`</td>
<td class="org-left">Short version of `help()`</td>
<td class="org-left">`?mtcars`</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">`??`</td>
<td class="org-left">Help for pattern<sup><a id="fnr.6" class="footref" href="#fn.6">6</a></sup></td>
<td class="org-left">`??mtcars`</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">`help.start()`</td>
<td class="org-left">Documentation webpage<sup><a id="fnr.7" class="footref" href="#fn.7">7</a></sup></td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>


<a id="orgb512199"></a>

## Concept summary

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">**Concept**</th>
<th scope="col" class="org-left">**Definition**</th>
<th scope="col" class="org-left">**Example/Reference**</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">64-bit</td>
<td class="org-left">Computing platform</td>
<td class="org-left">[64-bit computing](https://en.wikipedia.org/wiki/64-bit_computing)<sup><a id="fnr.8" class="footref" href="#fn.8">8</a></sup></td>
</tr>


<tr>
<td class="org-left">Raspberry Pi</td>
<td class="org-left">Small single-board computer</td>
<td class="org-left">[RaspberryPi.org](https://www.raspberrypi.org/)</td>
</tr>


<tr>
<td class="org-left">Function</td>
<td class="org-left">Execute predefined program</td>
<td class="org-left">In R: `license()`</td>
</tr>


<tr>
<td class="org-left">Open Source</td>
<td class="org-left">Code to freely view, edit, extend</td>
<td class="org-left">[Linux](https://opensource.com/resources/linux)</td>
</tr>


<tr>
<td class="org-left">Citation</td>
<td class="org-left">Referencing intellectual capital</td>
<td class="org-left">In R: `citation()`</td>
</tr>


<tr>
<td class="org-left">[Man page](https://en.wikipedia.org/wiki/Man_page)</td>
<td class="org-left">Unix-like help page format</td>
<td class="org-left">[Getting help with R](https://www.r-project.org/help.html)</td>
</tr>
</tbody>
</table>


<a id="org2e9ae85"></a>

## Challenges <code>[5/5]</code>

1.  [X] What is the difference between the licensing of Linux and the
    licensing of Android?
2.  [X] What are reasons why people care about, or ignore licensing
    issues? What's your personal point of view? What's your practice?
3.  [X] What does it take to "contribute" to the "[R Project](https://www.r-project.org/)"? Can
    anyone do that (who is skilled enough to do it??
4.  [X] Do you have to cite software that you use in your work?
    E.g. would you cite Java when writing an essay with results
    obtained with a Java program that you wrote yourself? Tip: do
    creators generally give credit for the tools they use?
5.  [X] How can you find out more about the `help.start()` function?
    How do I know where the documentation resides?

<div class="notes">
1.  The difference is that the Linux kernel (or core program, shared
    by all Linux distributions) is one piece of open source software
    that was developed by a group of volunteers (and started by
    [Linux Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds)), while "Android is an operating system for
    mobile devices which is based on the [Linux](https://opensource.com/resources/linux) kernel. While
    primarily developed by Google, the various components that make
    up Android are released under open source licenses, allowing
    others to create their own derivatives."  ([Source](https://opensource.com/tags/android)) Follow-up
    issues: Linux distributions; OS derivative. Version control and
    "crowdsourced" development; Git (another Torvalds creation) and
    GitHub.
2.  People ignore it because they don't like to think about
    ownership, or because they are used to thinking of all software
    as free (or as not free); they begin to care when they develop
    their own software, or when software they got used to is
    suddenly altered, disappears or costs something because of a
    licensing issue. Personally, I believe that open source software
    has great advantages - security is one - and some
    disadvantages - reliance and dependency on community. As a
    physics student, I grew up in the 1990s using "free" software,
    and I liked it. I do not think though that open source should
    always mean "at no cost" - instead, I believe people should give
    back (just not necessarily in the form of money to a
    corporation). But there are many ways of giving and giving back.
3.  As you can [read here](https://www.r-bloggers.com/2011/07/contributions-to-the-r-project/), the R Project (then) consisted of an "R
    Core Group, 21 volunteer statisticians and computer scientists
    from around the world [and] an ecosystem of R enthusiasts and
    developers who contribute to the project in other ways. [&#x2026;]
    This ecosystem continues to thrive with new packages being
    created at an exponential rate." This picture, taken in 2011, is
    unchanged in 2021, except that there are now (free) books about
    it, like "[R Packages](https://r-pkgs.org/)" by veteran developer Hadley Wickham (also
    the author of the `ggplot2` package, among many others. Here's
    also a [shorter tutorial](https://cran.r-project.org/doc/contrib/Leisch-CreatingPackages.pdf) from the R Project itself.
4.  This is a tricky question. The `citation()` function in R itself
    suggests that you should cite R if you used it. This [MIT library
    guide](https://libguides.mit.edu/c.php?g=551454&p=3900280) confirms the notion: "Cite the software that was used in
    your research, including all software that was used to generate
    and analyze data." But does this include the operating system?
    Should I include Linux just because my R program runs on a
    computer that, at the time, ran the Linux operating system? The
    answer is that the software needs to have been essential for the
    data operations. If I load the datasets into R and use its
    visualization routines, and the functionality of additional R
    packages, then I must cite all of them<sup><a id="fnr.9" class="footref" href="#fn.9">9</a></sup>. The same software would
    have run just the same on a Linux, a Windows or a MacOS
    computer - I don't have to cite them, too. However, as you can
    see, you need to think about the actual dependency of the
    creative part of your work (that is the part for which you, and
    only you, are responsible). If in doubt, rather cite
    superfluously, than suppress a citation.  See also: [FORCE11](https://www.force11.org/software-citation-principles)
    software citation principles (2016).
5.  To find out more about `help.start()`, type e.g. `??help.start`
    (for a short), or `?help.start` for a longer help page. To
    validate where your R documentation resides, check the status
    bar of your browser after opening the help page. On my computer,
    it says: `http://127.0.0.1:19591/doc/html/index.html` The URL
    `127.0.0.1` means that I am local (on my machine) - I can also
    replace it by `localhost` (check that!). The number `19591`
    after the address is the [port](https://computer.howstuffworks.com/web-server8.htm).

</div>


# Footnotes

<sup><a id="fn.1" href="#fnr.1">1</a></sup> Norm Matloff, the author of "fasteR" has also written a long
essay discussing the issues with the popular "Tidyverse", which is a
bundle of R packages (= library functions and datasets) including
e.g. `dplyr`, `tidyr` and others. It's fun to read and goes quite deep
into (open source) software development issues: see
"[TidyverseSceptic](https://github.com/matloff/TidyverseSkeptic)". Shortest summary: code using the "Tidyverse"
depends on (too) many functions (to remember), is hard to debug, and
obstructs already existing solutions at the expense of "trendy" ones.

<sup><a id="fn.2" href="#fnr.2">2</a></sup> This is the site on C++ created by its creator, Bjarne
Stroustrup. His book "[Programming-Principles and Practice Using C++](https://www.stroustrup.com/programming.html)"
is highly recommended if you want to get (self) started in this
important language (which I had to learn - and teach - during my PhD).

<sup><a id="fn.3" href="#fnr.3">3</a></sup> This is an excellent free course from DataCamp that introduces
what most of EDA is actually about (apart from cleaning data sets for
processing): visualization.

<sup><a id="fn.4" href="#fnr.4">4</a></sup> Here is a simple example of a function in R that only prints out
"Hello, world":

    f <- function() print("Hello World") # define function
    f()  # call function

    [1] "Hello World"

<sup><a id="fn.5" href="#fnr.5">5</a></sup> `apt` is the Ubuntu Linux package manager. This command asks for
an update of all updatable packages installed on this computer. Won't
work for Windows or for MacOS.

<sup><a id="fn.6" href="#fnr.6">6</a></sup> You use `??` for example if you cannot remember the name of a
dataset or a function, or if you need to know if a name is used in
different packages - this is often the case, try e.g. `filter`.

<sup><a id="fn.7" href="#fnr.7">7</a></sup> This is a web-based way of getting all kinds of information
specific to your version and implementation of R on your computer,
e.g. the packages installed, but also more general information on
import/export of datasets.

<sup><a id="fn.8" href="#fnr.8">8</a></sup> The current trend is no longer to increase the memory
instruction set but in designing efficient [multi-core](https://en.wikipedia.org/wiki/Multi-core_processor#Trends) processing
systems, in which concurrency of processes is optimized rather than
simultaneous addressing via a memory bus of 8, 32, 64 or more bits.

<sup><a id="fn.9" href="#fnr.9">9</a></sup> R packages always carry the information on how to cite them as
part of their documentation.
