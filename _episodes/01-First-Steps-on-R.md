---
title: "First Steps on R"
teaching: 10
exercises: 10
questions:
- "What is R, and why is important to learn to use it?"
- "What types of data does the R language has?"

objectives:
- "Understand why R is important."
- "Describe the purpose and use of each panel in the RStudio IDE"
- "Locate buttons and options in the RStudio IDE"
- "Define a variable"
- "Assign data to a variable"

keypoints:
- "R is a programming language"
- "RStudio is a useful tool for script writing and data-management."
- "A variable can temporarily store data."
---


*It takes courage to sail in uncharted waters*
  -Snoopy

## RStudio setup 

### What is R, and what can it be used for?

"R" is used to name a programming language and the 
software that reads and interprets the instructions written on the 
scripts of this language. Is specialized in statistical 
computing and graphics. RStudio is the most popular program for script writing and interaction with R software.

R uses a series of written commands, which is great, believe us! 
If you rely on clicking, pointing, and remembering where and 
why to point here or click there, mistakes are prone to occur. 
Moreover, if you manage to get more data, it is easier to just
*re-run* your script to obtain results. Also, working with scripts 
makes the steps you follow for your analysis clear and shareable. 
Here are some of the advantages of working with R:  

- R code is reproducible
- R produces high-quality graphics
- R has a large community
- R is interdisciplinary 
- R works on data of all colors and sizes
- R is free!

### A nautical chart of RStudio 

RStudio is an [Integrated Development Environment(IDE)](https://en.wikipedia.org/wiki/Integrated_development_environment#:~:text=An%20integrated%20development%20environment%20(IDE,automation%20tools%20and%20a%20debugger.)) 
which we will use to write code,
navigate the files from our computer/cloud, try code, inspect the variables we are 
going to create, and visualize our plots.

Here is what you may look at the first time you open RStudio:

<a href="{{ page.root }}/fig/Welcome_R.png" >
  <img src="{{ page.root }}/fig/Welcome_R.png" alt="RStudio graphic interface described bellow."  width="80%" height="55%" />
</a>


The figure shows the RStudio interface. The three windows that appear 
on the screen provide us with a space in which we can see our console
(left side window) where the orders we want to execute are written, observe 
the generated variables (upper right), and a series of subtabs (lower right): 
**Files** shows us files that we have used, **Plots** shows us graphics that we 
are generating, **Packages** shows the packages that we have downloaded, **Help** 
it gives us information on packages, commands, and/or functions that we do not 
know, but works only with an internet connection, and **Viewer** shows a results 
preview in R markdown files.

If we click on the option `File`/`New File`/`R Script`, we open up a script and
we get what we can call an _RStudio nautical chart_

<a href="{{ page.root }}/fig/Welcome_Rscript.png">
  <img src="{{ page.root }}/fig/Welcome_Rscript.png" alt="
A graphic interphase window with four panels.
A the top left, a new panel with an R script called *Untitled1* 
is added from the previous image, 
so now there are four panels inside the Rstudio graphic interphase window"  width="80%" height="55%"/>
</a>

RStudio interface with a new panel is shown. Clockwise from top left: Empty script,
Environment/History/Connections/Tutorial, Files/Plots/Packages/Help/Viewer,
Console/Terminal/Jobs. You can enter your online RStudio to see your environment.
Let's copy your instance address into your browser (Chrome or Firefox) and login into Rstudio. 
The address should look like this:  `http://ec2-3-235-238-92.compute-1.amazonaws.com:8787/` Although 
data are already stored in your instance, in case you need to you can download them [here](https://drive.google.com/file/d/15dW1sQCIhtmCUvS0IUOMPBH5m1gqNB0m/view?usp=sharing).

### Review of the setup

As we have revisited throughout the lesson, maintaining related data in a single folder
is desirable. In RStudio, this folder is called the **working directory**. It is where R will be looking 
for and saving your files. If you need to check where your working directory is located use `getwd()`.
If your working directory is not what you expected(*i.e. ~/dc_workshop/taxonomy/*), it can always be changed by clicking on the blue 
gear icon:
<a href="https://user-images.githubusercontent.com/67386612/118722611-f7f59400-b7f1-11eb-8ca9-a72561f9c529.png">
  <img src="https://user-images.githubusercontent.com/67386612/118722611-f7f59400-b7f1-11eb-8ca9-a72561f9c529.png" alt="settings icon" />
</a> on the `Files` tab, pick the option _Set As Working Directory_. Alternatively, you can use the `setwd()` command for changing it.

Let's use these commands to set our working directory where we have stored our files from the previous 
lessons:

~~~
> setwd("~/dc_workshop/taxonomy/")
~~~
{: .language-r}

## Having a dialogue with R

There are two main paths to interact with R in RStudio:
* Using the console.
* Creating and editing script files.

The console is where commands can be typed and executed immediately, and where the 
results from executed commands will be displayed (like in the Unix shell). If R is ready to accept commands, the R console shows
the `>` prompt. You can type instructions directly into the console and press "Enter", but they will 
be forgotten when you close the session.

For example, let's do some math and save it in R objects. We can store values in variables by
using the assignment operator `<-`:
~~~ 
> 4+3
> addition <- 4+3
> subtraction <- 2+1
> total <- addition -subtraction
> total
~~~
{: .language-r}

What would happen if you tap `ctrl` + `l`? Without the lesson page, can you remember what numbers the sum is made of in the variable `addition`?
**Reproducibility** is in our minds when we program (and when we do science). For this purpose, 
is convenient to type the commands we want to save in the script editor, and save the script periodically. 
We can run our code lines in the script by the shortcut `ctrl` + `Enter` 
(on Mac, `Cmd` + `Return` will work). Thus, the command on the current line or the instructions
in the currently selected text will be sent to the console and will be executed.

Time can be the enemy or ally of memory. We want to be sure to remember why we wrote the commands
in our scripts, so we can leave comments(lines of no executable text) by beginning a line with `#`:
~~~
# Let's do some math in RStudio. How many times a year do the supermarkets change the bread that they use for
# display? if they change it every 15 days:
> 365/15
~~~
{: .language-r}
~~~
[1] 24.3333
~~~
{: .output}
