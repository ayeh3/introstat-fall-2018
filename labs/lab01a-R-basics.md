Lab 1a: Getting started with R and RStudio
================

> ### Learning Objectives:
> 
>   - Get started with R as a scientific calculator
>   - Understand pane layout of RStudio
>   - Understand the help documentation in R
>   - How to install packages
>   - Get to know markdown syntax

-----

## R and RStudio

  - Make sure everybody has installed **R**
      - R for Mac: <https://cran.r-project.org/bin/macosx/>
      - R for windows: <https://cran.r-project.org/bin/windows/base/>
  - Make sure everybody has installed **RStudio**
      - RStudio download:
        <https://www.rstudio.com/products/rstudio/download/>
  - We are going to use mainly RStudio, but you should know that R is
    not the same as RStudio. The latter is just an integrated
    development environment (IDE).

-----

## R as a scientific calculator

Launch RStudio and notice the default position of the panes (or panels):

  - Console (entire left)
  - Environment/History (tabbed in upper right)
  - Files/Plots/Packages/Help (tabbed in lower right)

**FYI:** you can change the default location of the panes, among many
other things: [Customizing
RStudio](https://support.rstudio.com/hc/en-us/articles/200549016-Customizing-RStudio).
If have no experience working with R/RStudio, you don’t have to
customize anything right now. It’s better if you wait some days until
you get a better feeling of the working environment. You will probably
be experimenting (trial and error) with the customizing options until
you find what works for you.

### First contact with the R console

Let’s start typing basic things in the *console*, using R as a
scientific calculator.

For instance, consider the monthly bills of Leia (a stats undergrad
student): cell phone $80, transportation $20, groceries $527, gym $10,
rent $1500, other $83. You can use R to find Leia’s total expenses:

``` r
# total expenses
80 + 20 + 527 + 10 + 1500 + 83
```

    ## [1] 2220

Often, it will be more convenient to create **objects** or **variables**
that store one or more values. To do this, type the name of the
variable, followed by the assignment operator `<-`, followed by the
assigned value. For example, you can create an object `phone` for the
cell phone bill, and then inspect the object by typing its name:

``` r
phone <- 80
phone
```

    ## [1] 80

All R statements where you create objects, “assignments”, have this
form:

``` r
object <- value
```

this means you assign a `value` to a given `object`; you can read the
previous assignment as “phone gets 80”.

RStudio has a keyboard shortcut for the arrow operator `<-`: `Alt` + `-`
(the minus sign).

Notice that RStudio automagically surrounds `<-` with spaces, which
demonstrates a useful code formatting practice. So do yourself (and
others) a favor by ALWAYS surrounding an assignment operator with
spaces.

  - Make more assignments to create variables `transportation`,
    `groceries`, `gym`, `rent`, and `other` with their corresponding
    amounts

  - Now that you have all the variables, create a `total` object with
    the sum of the expenses:

  - Assuming that Leia has the same expenses every month, how much would
    she spend during a school “semester”? (assume the semester involves
    five months)

  - Maintaining the same assumption about the monthly expenses, how much
    would Leia spend during a school “year”? (assume the academic year
    is 10 months)

### Object Names

There are certain rules you have to follow when creating objects and
variables. Object names cannot start with a digit and cannot contain
certain other characters such as a comma or a space. You will be wise to
adopt a convention for demarcating words in names.

``` r
i_use_snake_case
other.people.use.periods
evenOthersUseCamelCase
```

The following are invalid names (and invalid assignments)

    # cannot start with a number
    5variable <- 5
    
    # cannot start with an underscore
    _invalid <- 10
    
    # cannot contain comma
    my,variable <- 3
    
    # cannot contain spaces
    my variable <- 1

This is fine but a little bit too much:

``` r
this_is_a_really_long_name <- 3.5
```

### Functions

R has many functions. To use a function type its name followed by
parenthesis. Inside the parenthesis you pass an input. Most functions
will produce some type of output:

``` r
# absolute value
abs(10)
abs(-4)

# square root
sqrt(9)

# natural logarithm
log(2)
```

### Comments in R

All programming languages use a set of characters to indicate that a
specifc part or lines of code are **comments**, that is, things that are
not to be executed. R uses the hash or pound symbol `#` to specify
comments. Any code to the right of `#` will not be executed by R.

``` r
# this is a comment
# this is another comment
2 * 9

4 + 5  # you can place comments like this
```

### Case Sensitive

R is case sensitive. This means that `phone` is not the same as `Phone`
or `PHONE`

``` r
# case sensitive
phone <- 80
Phone <- -80
PHONE <- 8000

phone + Phone
```

    ## [1] 0

``` r
PHONE - phone
```

    ## [1] 7920

### Your turn

Take your objects (i.e. variables) `phone`, `transportation`,
`groceries`, `gym`, `rent`, and `other` and pass them inside the
*combine* function `c()` to create a vector `expenses`

``` r
# your vector expenses
```

Now, use the graphing function `barplot()` to produce a barchart of
`expenses`:

``` r
barplot(expenses)
```

Find out how to use `sort()` to sort the elements in `expenses`, in
order to produce a bar-chart with bars in decreasing order. Also, see if
you can figure out how to display the names of the variables below each
of the bars. Also optional, see if you can find out how to display the
values of each variable at the top of each bar.

-----

## More about RStudio

You will be working with RStudio a lot, and you will have time to learn
most of the bells and whistles RStudio provides. Think about RStudio as
your “workbench”. Keep in mind that RStudio is NOT R. RStudio is an
environment that makes it easier to work with R, while taking care of
many of the little tasks than can be a hassle.

### Getting help

Because we work with functions all the time, it’s important to know
certain details about how to use them, what input(s) is required, and
what is the returned output.

There are several ways to get help.

If you know the name of a function you are interested in knowing more,
you can use the function `help()` and pass it the name of the function
you are looking for:

``` r
# documentation about the 'abs' function
help(abs)

# documentation about the 'mean' function
help(mean)
```

Alternatively, you can use a shortcut using the question mark `?`
followed by the name of the function:

``` r
# documentation about the 'abs' function
?abs

# documentation about the 'mean' function
?mean
```

  - Understand and learn how to read the manual (i.e. help)
    documentation
      - Title
      - Description
      - Usage of function
      - Arguments
      - Details
      - See Also
      - Examples\!\!\!

`help()` only works if you know the name of the function your are
looking for. Sometimes, however, you don’t know the name but you may
know some keywords. To look for related functions associated to a
keyword, use double `help.search()` or simply `??`

``` r
# search for 'absolute'
help.search("absolute")

# alternatively you can also search like this:
??absolute
```

Notice the use of quotes surrounding the input name inside
`help.search()`

## Installing Packages

R comes with a large set of functions and packages. A package is a
collection of functions that have been designed for a specific purpose.
One of the great advantages of R is that many analysts, scientists,
programmers, and users can create their own pacakages and make them
available for everybody to use them. R packages can be shared in
different ways. The most common way to share a package is to submit it
to what is known as **CRAN**, the *Comprehensive R Archive Network*.

You can install a package using the `install.packages()` function. Just
give it the name of a package, surrounded by qoutes, and R will look for
it in CRAN, and if it finds it, R will download it to your computer.

``` r
# installing
install.packages("knitr")
```

You can also install a bunch of packages at once:

``` r
install.packages(c("readr", "ggplot2"))
```

Once you installed a package, you can start using its functions by
*loading* the package with the function `library()`

``` r
library(knitr)
```

### Your turn

  - Install packages `"stringr"`, `"RColorBrewer"`, and “`XML`”
  - Calculate: \(3x^2 + 4x + 8\) when \(x = 2\)
  - Calculate: \(3x^2 + 4x + 8\) but now with a numeric sequence for
    \(x\) using `x <- -3:3`
  - Find out how to look for information about math binary operators
    like `+` or `^` (without using `?Arithmetic`).
  - There are several tabs in the pane `Files, Plots, Packages, Help,
    Viewer`. Find what does the tab **Files** is good for?
  - What about the tab **Help**?
  - In the tab **Help**, what happens when you click the button with a
    House icon?
  - Now go to the tab **History**. What is it good for? and what about
    the buttons of its associated menu bar?
  - Likewise, what can you say about the tab **Environment**?

-----

## Introduction to Markdown

You will be using a specific type of source files known as *R markdown*
files. These files use a special syntax called **markdown**.

### Get to know the `Rmd` files

In the menu bar of RStudio, click on **File**, then **New File**, and
choose **R Markdown**. Select the default option (Document), and click
**Ok**.

**Rmd** files are a special type of file, referred to as a *dynamic
document*, that allows to combine narrative (text) with R code. Because
you will be turning in most homework assignments as `Rmd` files, it is
important that you quickly become familiar with this resource.

Locate the button **Knit HTML** (the one with a knitting icon) and click
on it so you can see how `Rmd` files are renderer and displayed as HTML
documents.

### Yet Another Syntax to Learn

R markdown (`Rmd`) files use
[markdown](https://daringfireball.net/projects/markdown/) as the main
syntax to write content. It is a very lightweight type of markup
language, and it is relatively easy to learn.

### Your turn

In RStudio’s menu bar select the `Help` tab. Then click on the option
`Markdown Quick Reference`.

Work through the markdown tutorial:
[www.markdown-tutorial.com](http://www.markdown-tutorial.com)

Your turn: After lab discussion, find some time to go through this
additional markdown tutorial
[www.markdowntutorial.com/](http://www.markdowntutorial.com/)

RStudio has a very comprehensive R Markdown tutorial: [Rstudio markdown
tutorial](http://rmarkdown.rstudio.com/)

-----

## Review Questions

Take a look at the following commands. Notice the difficulty of reading
code when assignment operators are not surrounded by spaces (Don’t do
this\!). Without typing the code on the console, try to guess what will
be the output:

    # example 1
    var<-3
    Var*2
    
    
    # example 2
    x<-2
    2x<-2*x
    
    
    # example 3
    sqrt4 <- sqrt(4)
    sqrt4
    
    
    # example 4
    a number <- 16
    
    
    # example 5
    "one number" <- 16
    `one number`
    one number

### RStudio working environment

Understand the **pane layout** (i.e. windows) of RStudio. What is the
purpose of the following panes?

  - Source
  - Console
  - Environment, History, etc
  - Files, Plots, Packages, Help, Viewer

Play with the customizing options of RStudio (appearance of source pane,
etc)

  - font
  - size
  - background
