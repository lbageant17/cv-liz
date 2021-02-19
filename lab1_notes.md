---
title: "Lab 1 Exercise"
author: "Liz Bageant"
date: "2/12/2021"
output: 
  html_document: 
    toc: true
    toc_depth: 3
    toc_float: true
---

<!-- The code below sets the global options for the code chunks. Global options can be modified by specifying something else in individual code chunks. It is handy to use these global settings, but not essential to knit document. -->
```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = FALSE)
```

# Today's exercises
Today we're tinkering with Rmarkdown to get more practice. 

## Misc tips

+ Make explicit line breaks with `<br>`. Multiple "enters" won't register as multiple line breaks.
<br>
<br>
+ Block quotes can be made with one or more `>` like this:

>>> this is my block quote

+ If you want to make a comment in text form and not have it show up in your knitted document, you can.... <!-- hide it like this --> (comment is hidden)
+ Sometimes the formatting doesn't work the way you want it to work. If you add two spaces after a line break or whatever is on the previous line, sometimes that works. In other cases putting an extra space by hitting enter (not with the line break `<br>`)
+ File names with spaces can give you random problems. Avoid it.
+ TRUE and FALSE are always all caps and no quotation marks. Other arguments like "hide" need to be in quotation marks.

+ Putting numbers in text witout hard-coding them.
  * If we want to describe the dimensions of our dataset without hard-coding: the `cars` dataset has `r nrow(cars)` observations and `r ncol(cars)` variables. 
  
## Editing the YAML header
Edit the YAML header to createt a table of contents by saying `toc: true`. 
  + `toc_depth: ` tells us which level of header to include in the TOC. 
  + `toc_float: true` makes it a cute box instead of just text.  
  + Indentation matters!  
  + ![](YAML.png)


Output options:
  + html_document
  + pdf (what is code exactly?)
  + word_document
  + slides (what is code exactly?)

<br>
<br>

## Adding images
1. Putting a photo of something using a URL
<br>
Using an online image....
![](https://media1.s-nbcnews.com/j/newscms/2019_46/3101906/191114-volkswagen-id-space-vizzion-concept-ew-818p_668c65c0dd8ab0befbec99aac57f280f.fit-2000w.jpg)

2. Or using an image from your computer. Copy file path or, if the image in in your working directory, you can just write the file name.

![Millie!](IMG_0586.jpeg)

3. Using `knitr::include_graphics()`
There is a tutorial in the [lab notes](https://nt246.github.io/NTRES-6100-data-science/lab1-rmarkdown.html) demosntrating how to do this.

<br>
<br>
<br>


## Embedding R code chunks
Four ways:

+ Ctrl+alt+i
+ Code > Insert chunk
+ Green C button at top of Rstudio
+ Manually write the backticks, curly  brackets, etc.


```{r pressure, echo = TRUE}
plot(pressure)
```



You can embed an R code chunk like this. 

```{r cars, echo = FALSE}
summary(cars)
```


If we want to embed code, but not the output, we would add `eval = FALSE'  or results = "hide"

```{r cars_no_graph, results = "hide"}
summary(cars)
```
<br>

If we want to embed code and hide code and output we would say `include = FALSE` (There is a code chunk in the rmd doc, but you can't see it in the knitted version)
```{r cars_no_graph_no_chunk, include = FALSE}
summary(cars)
```
<br>

## Including Plots


Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

