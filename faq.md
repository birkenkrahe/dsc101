
# Table of Contents

1.  [Are we going to use RStudio?](#orgadf0cc8)
2.  [Which editor do you use?](#org65f93c1)


<a id="orgadf0cc8"></a>

# Are we going to use RStudio?

No. [RStudio](https://rstudio.com/) is worth checking out, and it may well be what you use
later in your data science career, but I think it is much too
complex for beginners, and not really necessary at all. See
screenshot:

![img](https://github.com/birkenkrahe/dsc101/blob/main/wiki/rstudio.png)

RStudio is a so-called "IDE" (Integrated Development Environment) -
it presents a file editor (to create R programs, or notebooks), an R
console (to enter commands interactively), a graphical output device
(for plots), a file explorer, and an environment explorer (for
loaded variables etc.), and more. It's a tool created for
professionals and developers of packages<sup><a id="fnr.1" class="footref" href="#fn.1">1</a></sup>.

I want you to focus on the basics. As a beginner, this will serve
you best, I believe. It's a little like learning to drive on gear
shift, and then upgrading to automatic transmission.

I will however, show you RStudio, and we will also use it together
(optionally) during the session on "Literate Programming".

If you want to install RStudio on your computer, here is an
excellent [beginner's tutorial](https://techvidvan.com/tutorials/install-r/).


<a id="org65f93c1"></a>

# Which editor do you use?

I use the free [Emacs](https://www.gnu.org/software/emacs/) editor. For R, I use Emacs + [ESS](https://ess.r-project.org/) ("Emacs Speaks
Statistics"), for general notebooking and task management
and&#x2026;everything really, I use Emacs + ESS + [Org-mode](https://orgmode.org/) (a
general-purpose task manager inside Emacs, first developed by
physicists like me). For slides, I use the [reveal.js](https://github.com/hakimel/reveal.js/) (JavaScript)
framework (generates HTML), or [org-tree-slide](https://github.com/takaxp/org-tree-slide) (for presenting
straight from Org-mode).

Emacs is hands down the best editor in the world, written in LISP,
one of the earliest programming languages for AI research, and the
second oldest language in widespread use (after FORTRAN).

They say the learning curve of this "complex beast" ([Petersen, 2019](https://masteringemacs.org/article/beginners-guide-to-emacs))
is steep but don't believe it.  Here is an link to [get started with
Emacs easily](https://opensource.com/article/20/3/getting-started-emacs) (Kenlon, 2019). Tale a look!

Here is a 2021 "[Introduction to Emacs Speaks Statistics](https://ess-intro.github.io/)" site with
lots of additional information.


# Footnotes

<sup><a id="fn.1" href="#fnr.1">1</a></sup> It is unfortunate, that people (usually newbies) believe that "R
= RStudio = Tidyverse". This has to do with the great marketing
successes of RStudio (the company behind the product). Don't get me
wrong: there are many wonderful things about RStudio (e.g. it's Open
source). But you don't need it and it has a "lock-in" effect. I
e.g. use **Emacs + ESS + Org-mode** instead, but I also would not
recommend it for beginners.
