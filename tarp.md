
# Table of Contents

1.  [The Art Of R Programming](#org13dce30)
2.  [Introduction](#orgcfe836c)
    1.  [Why R](#org76e9585)
    2.  [GUI vs CLI](#orgf4eb0f0)
    3.  [OOP / Functional Programming](#org7bde0e8)
    4.  [Concept summary](#org3783869)
    5.  [Code summary](#orgf465bdd)
    6.  [Exercises](#org3472516)
3.  [Getting started](#orgbc9a2cb)
    1.  [How to Run R](#org0acdf36)
        1.  [Command line](#orgd044d92)
        2.  [Batch mode](#org739f7dd)
    2.  [A First R Session](#org80333af)
        1.  [Creating vectors](#org9e52e9a)
        2.  [Subsetting vectors](#org8443e7c)
        3.  [Statistical functions](#org577fa33)
        4.  [Built-in datasets](#org1c5850c)
        5.  [Creating histograms](#org4382b45)
        6.  [R graphics display](#org7513b3c)
        7.  [Quit R](#org4f854ea)


<a id="org13dce30"></a>

# The Art Of R Programming

-   Free version (2009) [Internet archive PDF](https://archive.org/details/Norman_Matloff___The_Art_of_R_Programming/mode/2up)
-   [Kindle (2011)](https://lesen.amazon.de/?asin=B00683GXUO&language=de-DE)
-   Real datasets and extended examples
-   Programmer's sensibililities
-   Debugging and parallel programming
-   Interfacing with other languages
-   Performance tuning for big data


<a id="orgcfe836c"></a>

# DONE Introduction


<a id="org76e9585"></a>

## Why R

> yauh peng, yauh leng ("Both inexpensive and beautiful")
> &#x2013;Cantonese proverb

1.  Public domain implementation of S
2.  De facto standard among professional statisticians
3.  Superior to comparable commercial products
4.  Available for Windows, MacOS, and Linux
5.  Extensible through library packaging
6.  Has OOP and functional programming features
7.  Saves data and command history between sessions
8.  Has a large and helpful user community
9.  Allows for interactive data exploration via command-line
10. Superior graphics capabilities


<a id="orgf4eb0f0"></a>

## GUI vs CLI

Popular GUIs (that I have also used) include:

-   RStudio<sup><a id="fnr.1" class="footref" href="#fn.1">1</a></sup>
-   ESS for Emacs<sup><a id="fnr.2" class="footref" href="#fn.2">2</a></sup>
-   VS Code<sup><a id="fnr.3" class="footref" href="#fn.3">3</a></sup>


<a id="org7bde0e8"></a>

## OOP / Functional Programming

-   R is an **object-oriented** (OOP) programming language: (1)
    functions like `lm` (regression) return an object whose stats
    elements you can then extract (encapsulation); (2) a function can
    be applied to different input types (polymorphism), e.g. [`plot()`](https://www.rdocumentation.org/packages/graphics/versions/3.6.2/topics/plot)
    applied to numbers yields a simple plot, while applied to the
    output of a regression analysis, yields a set of plots
    representing different analysis aspects.

-   R is also a **functional** programming (FP) language: you can
    express iterative behavior (otherwise implemented via loops)
    implicitly, yielding: clearer, more compact code, faster
    execution speed, less debugging of simpler code, and easier
    transition to parallel programming - which is crucial in today's
    hardware environment. Check out the example in the code chunk
    below<sup><a id="fnr.4" class="footref" href="#fn.4">4</a></sup>.

    nrow(subset(mtcars,mpg>18))


<a id="org3783869"></a>

## Concept summary

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">**Concept**</th>
<th scope="col" class="org-left">**Description**</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">OOP</td>
<td class="org-left">Object-oriented programming</td>
</tr>


<tr>
<td class="org-left">FP</td>
<td class="org-left">Functional programming</td>
</tr>


<tr>
<td class="org-left">CLI</td>
<td class="org-left">Command Line Interface (shell/console)</td>
</tr>


<tr>
<td class="org-left">GUI</td>
<td class="org-left">Graphical User Interface</td>
</tr>


<tr>
<td class="org-left">Emacs</td>
<td class="org-left">Extensible Lisp-based text editor</td>
</tr>


<tr>
<td class="org-left">IDE</td>
<td class="org-left">Integrated Development Environment</td>
</tr>


<tr>
<td class="org-left">RStudio</td>
<td class="org-left">Popular IDE for R</td>
</tr>
</tbody>
</table>


<a id="orgf465bdd"></a>

## Code summary

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">**Command**</th>
<th scope="col" class="org-left">**Description**</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">`subset()`</td>
<td class="org-left">Extract rows</td>
</tr>


<tr>
<td class="org-left">`nrow()`</td>
<td class="org-left">Count rows</td>
</tr>


<tr>
<td class="org-left">`plot()`</td>
<td class="org-left">Plotting</td>
</tr>
</tbody>
</table>


<a id="org3472516"></a>

## Exercises

1.  Check out the [RStudio](https://www.rstudio.com/), [Emacs](https://www.gnu.org/software/emacs/) and [ESS](https://ess.r-project.org/) sites (see FAQ)
2.  How do you decide between CLI and GUI (IDEs)?
3.  How do you decide between different IDEs?
4.  Install R on your computer from [CRAN](https://www.r-project.org/) ([tutorial](https://www.datacamp.com/community/tutorials/installing-R-windows-mac-ubuntu))


<a id="orgbc9a2cb"></a>

# Getting started


<a id="org0acdf36"></a>

## How to Run R


<a id="orgd044d92"></a>

### Command line

1.  Executing R code from the command line

        mean(abs(rnorm(100)))

2.  Executing R file with `source()`:

    -   Put the previous command in a file `m.R`
    -   Run it from the command line
    
        source("m.R", echo=TRUE)
    
    The `echo` argument prints expressions, see `?source`.


<a id="org739f7dd"></a>

### Batch mode

-   Batch operation - find out more with `R --help`
-   Sample code: save histogram as PDF file
-   `#` marks a comment (ignored by R)
-   Write the code into a file `z.R`

    pdf("xh.pdf") # save graph in PDF file
    hist(rnorm(100)) # generate histogram of 100 random numbers
    dev.off() # close graphical device

-   Run from the OS shell with `R CMD BATCH z.R`
-   Open graphical device with `pdf()`
-   Close graphical device with `dev.off()`
-   Produces `.Rout` log file and `xh.pdf` output


<a id="org80333af"></a>

## A First R Session


<a id="org9e52e9a"></a>

### Creating vectors

-   Create data set (vector object) with `c()`
-   `c()` is the concatenation function
-   Confirm it's a vector with `is.vector()`
-   Print it by typing its name

    x <- c(1,2,4)
    is.vector(x)
    x

-   Create a vector of vectors `q`

    q <- c(x,x,8)
    q


<a id="org8443e7c"></a>

### Subsetting vectors

-   Access vector elements with `[ ]`
-   The argument selector is an index or subscript
-   Elements of R vectors start from `1`, not `0`

    x # print vector x
    x[3] # extract the third element
    x[2:3] # extract elements 2 through 3


<a id="org577fa33"></a>

### Statistical functions

-   Compute the mean of `x` with `mean()`
-   Compute the standard deviation of `x` with `sd()`
-   Remember what "mean" and "standard deviation" are?<sup><a id="fnr.5" class="footref" href="#fn.5">5</a></sup>

    y <- mean(x)  # comput the mean of x and store in y
    y  # print y
    m <- (x[1]+x[2]+x[3])/length(x)  # check that it's the mean
    m
    identical(m,y)  # another way of checking
    sd(x)


<a id="org1c5850c"></a>

### Built-in datasets

-   R has built-in datasets like `Nile`
-   Check all loaded datasets with `data()`<sup><a id="fnr.6" class="footref" href="#fn.6">6</a></sup>
-   Compute the mean and standard deviation of `Nile`
-   Check the object type of `Nile` with `class`
-   Print all of the dataset by typing its name

    mean(Nile)  # mean value
    sd(Nile) # standard deviation
    class(Nile)  # Nile is a "time series"
    Nile

You can find out more about `Nile` with `?Nile` or `help(Nile)`


<a id="org4382b45"></a>

### Creating histograms

-   Plot a histogram of the data with `hist()`

    setwd("~/OneDrive/2021_Fall/dsc101/tarp/")
    hist(Nile) # print histogram of Nile to file

-   Customize the histogram with arguments
-   `breaks` specifies the number of bins
-   `color` specifies the color of the bars
-   `border` specifies the bar border color
    
        hist(Nile, breaks=12, col="blue", border="white")


<a id="org7513b3c"></a>

### R graphics display

-   The graph is written to the same device
-   Check device list with `dev.list()`
    
        dev.list() # two devices are open right now

-   One device was created with (graphics) `:file`
-   The other was created with (direct) `output`
-   You can delete devices with `dev.off()`


<a id="org4f854ea"></a>

### Quit R

-   When quitting with `q()`, you can save the workspace
-   This creates files `.RData` and `.Rhistory`
-   `q()` will not work in a notebook chunk


# Footnotes

<sup><a id="fn.1" href="#fnr.1">1</a></sup> DSC101 FAQ: [Are we going to use RStudio?](file:///home/marcus/OneDrive/2021_Fall/dsc101/faq/faq.md)

<sup><a id="fn.2" href="#fnr.2">2</a></sup> DSC101 FAQ: [Which editor do you use?](file:///home/marcus/OneDrive/2021_Fall/dsc101/faq/faq.md)

<sup><a id="fn.3" href="#fnr.3">3</a></sup> Microsoft's (semi-commercial) [Visual Studio (VS) Code](https://en.wikipedia.org/wiki/Visual_Studio_Code) editor
seems quite popular among developers across different languages. I
have not tried it but the setup for R seems forbiddingly complicated
(as of March, 2020, according to [this blog post](https://www.r-bloggers.com/2020/03/setting-up-r-with-visual-studio-code-quickly-and-easily-with-the-languageserversetup-package/)).

<sup><a id="fn.4" href="#fnr.4">4</a></sup> There are two functions in play here: `subset()` extracts all
records (rows) of the dataset `mtcars` whose variable `mpg` is greater
than 18 and puts them into a dataset. The function `nrow()` then
counts the rows of that dataframe.

<sup><a id="fn.5" href="#fnr.5">5</a></sup> The [arithmetic mean](https://en.wikipedia.org/wiki/Arithmetic_mean) \(\mu(x)\) is a measure for the center of a
set of values. The [standard deviation](https://en.wikipedia.org/wiki/Standard_deviation) \(\sigma(x)\) is a measure for the
dispersion of a set of values.

<sup><a id="fn.6" href="#fnr.6">6</a></sup> Check a particular package by passing the name as an argument to
`data()`, e.g. `data(package="datasets")` for the built-in datasets.
