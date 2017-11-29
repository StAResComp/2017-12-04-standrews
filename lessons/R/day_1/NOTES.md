# `NOTES.md` - `R` lesson day one
These notes are for the tutor on day one of the two-day `R` Software Carpentry course, taught 5th December 2017 at the University of St Andrews.

# Things to remember

To clear a console environment in `R`:

```R
rm(list=ls())
```

# Start the slides

## TITLE

* Programming in `R`: Part One

## ETHERPAD

* Please use the Etherpad for the course

## SECTION 01: Introduction to `R` and `RStudio`

**SLIDE: Learning Objectives**

* We're going to talk in general terms about **WHAT `R` and `RSTUDIO` are**.
* We're also going to discuss **WHAT MAKES THEM DIFFERENT FROM SOME OTHER TOOLS** you might already use for similar tasks, like `Excel`

----

**SLIDE: What is `R`?**

* `R` is a **PROGRAMMING LANGUAGE**, and the **SOFTWARE** that runs programs written in that language.
* `R` is **AVAILABLE ON ALL PLATFORMS**
* This can sometimes be confusing - **IF AT ANY POINT I AM UNCLEAR, PLEASE ASK!**

* **HAS ANYONE IN THE ROOM USED `R` BEFORE? - GREEN STICKY**
    * If anyone has used `R`, please could you be available to help one of your neighbours who has not, if they have any questions. Look around you - if there's someone nearby with a green sticky, say 'hi'!

* **WHY USE OR TEACH `R`?**
    * `R` is **FREE**, and very **WIDELY-USED** across a range of disciplines.
    * There are **MANY USEFUL PACKAGES** or data analysis and statistics
    * It has excellent **GRAPHICS CAPABILITIES**
    * There is an international, friendly **COMMUNITY** across a range of disciplines, so it's easy to find local and online support

----

**SLIDE: But I already know `Excel`**

* I'm **NOT HERE TO CRITICISE `EXCEL`**. `Excel` is brilliant at what it's meant to do. It's **POWERFUL** and **INTUITIVE**.
* But **`R` HAS MANY ADVANTAGES FOR REPRODUCIBLE AND COMPLEX ANALYSIS**

* A key thing for reproducibility is that it **SEPARATES DATA FROM ANALYSIS**.
    * In `R`, when you do anything to the original data, that original data remains unmodified (unless you overwrite the file).
    * **POINT OF GOOD PRACTICE: RAW DATA SHOULD BE READ-ONLY**
    * In `Excel` however it's easy to overwrite data with copy-and-paste (and many bad things have happened as a result) - see Mike Croucher's talk for examples.

* Because **YOUR ANALYSIS IN `R` IS A PROGRAM**, every step is written down explicitly, and is transparent and understandable by someone else.
    * In `Excel`, there is no clear record of where you moved your mouse, or what you copied and pasted, and it's not immediately obvious how your formulas work.

* `R` code is **EASY TO SHARE AND ADAPT**, and to apply again to a different or a modified input dataset. It's easy to publish the analyses via online resources, such as GitHub.
* `R` code can also be **RUN ON EXTREMELY LARGE DATASETS**, quickly. That's much harder in `Excel`.

----

**SLIDE: What is `RStudio`?**

* `RStudio` is an **INTEGRATED DEVELOPMENT ENVIRONMENT** - which is to say it's a very powerful tool for writing and using `R` and programs in the `R` language.
    * It's available on **ALL PLATFORMS**
    * It's available as a webserver, too.

* On the left is a screenshot **WHILE I WAS WRITING THIS PRESENTATION IN RSTUDIO** on a Mac
* On the right is the Windows version, with an **EXAMPLE ANALYSIS AND VISUALISATION**

* You can use it to **INTERACT WITH `R` DIRECTLY TO EXPERIMENT WITH DATA**
* It has a **CODE/SCRIPT EDITOR FOR WRITING PROGRAMS**
* It has tools for **VISUALISING DATA**
* It has built-in **GIT INTEGRATION FOR MANAGING YOUR PROJECTS**

## SECTION 02: Getting To Know `RStudio`

**SLIDE: Learning Objectives**

* We need to get some **FAMILIARITY WITH OUR WORKING ENVIRONMENT**: the `RStudio` IDE
* Develop some **BEST PRACTICES FOR PROJECT MANAGEMENT** in general, and in `RStudio`
* We'll **BUILD UPON THE `GIT` LESSON** because `RStudio` integrates naturally with `git` to keep all your analysis and code under version control.
* We'll introduce `R` syntax, and **SEE HOW `R` REPRESENTS DATA** and how to **PROGRAM IN `R`**
* If we have time we'll deal with **MANAGING SOME OF THE MANY USEFUL PACKAGES** available in `R`

----

**SLIDE: `RStudio` overview - Interactive Demo**

* **START `RStudio`** (click icon/go into start menu and select RStudio/etc.)
    * **CHECK EVERYONE CAN START `RSTUDIO`**

![images/red_green_sticky.png](images/red_green_sticky.png)

* **REMIND PEOPLE THEY CAN USE RED/GREEN STICKIES AT ANY TIME**
* You should see **THREE PANELS**
    * Interactive `R` console: **you can type here and get instant feedback**
    * Environment/History window
    * Files/Plots/Packages/Help/Viewer: **interacting with files on the computer, and viewing help and some output**

* We're going to use `R` in the interactive console to get used to some of the features of the language, and `RStudio`. **DEMO CODE: ASK PEOPLE TO TYPE ALONG**
    * **THE RIGHT ANGLED BRACKET IS A PROMPT: `R` EXPECTS INPUT**
    * **TYPE THE CALCULATION, THEN PRESS RETURN**

```R
> 1 + 100
[1] 101
> 30 / 3
[1] 10
```

* **RESULT IS INDICATED WITH A NUMBER `[1]`** this indicates the line with output in it
* If you type an **INCOMPLETE COMMAND**, `R` will wait for you to complete it
    * **DEMO CODE**

```R
> 1 +
+ 
```

* The **PROMPT CHANGES TO `+` WHEN `R` EXPECTS MORE INPUT**
* You can either complete the line, or use `Esc` (`Ctrl-C`) to exit

```R
> 1 +
+ 6
[1] 7
> 1 + 
+ 

> 
```

* `R` obeys the usual **PRECEDENCE OPERATIONS** ( `(`, `**`/`^`, `/`, `*`, `+`, `-`)
    * **DEMO CODE: NOTE SPACES AROUND OPERATORS**

```R
> 3 + 5 * 2
[1] 13
> (3 + 5) * 2
[1] 16
> 3 + 5 * 2 ^ 2
[1] 23
> 3 + 5 * (2 ^ 2)
[1] 23
```

* **ARROW KEYS RECOVER OLD COMMANDS**
* **THE `HISTORY` TAB SHOWS ALL COMMANDS USED**
* `R` will report in **SCIENTIFIC NOTATION**
    * **CHECK THAT EVERYONE KNOWS WHAT SCIENTIFIC NOTATION IS**

![images/red_green_sticky.png](images/red_green_sticky.png)

```R
> 2 / 1000
[1] 0.002
> 2 / 10000
[1] 2e-04
> 5e3
[1] 5000
```

* `R` has many **STANDARD MATHEMATICAL FUNCTIONS**
* **FUNCTION SYNTAX**
     * type the function name
     * open parentheses
     * type input value
     * close parentheses
     * press return
     * **DEMO CODE**

```R
> sin(1)
[1] 0.841471
> log(1)
[1] 0
> log10(10)
[1] 1
> log(10)
[1] 2.302585
```

* How do we learn more about a function, or the difference between `log()` and `log10()`?
* **USE `R` BUILT-IN HELP**
    * Type `?` then the function name
    * Scroll to the bottom of the page to find example code

```R
> ?log
```

* This brings up help in the **HELP WINDOW**
* You can also use the **SEARCH BOX** at the top of the help window (try `sin()`)
* If you're not sure about spelling, the editor has **AUTOCOMPLETION** which will suggest all possible endings for something you type (try `log`) - **USE TAB TO SEE AUTOCOMPLETIONS**

* We can do **COMPARISONS** in `R`
    * Comparisons return `TRUE` or `FALSE`. **DEMO CODE**
    * **NOTE:** when comparing numbers, it's better to use `all.equal()` (*machine numeric tolerance*)

```R
> 1 == 1
[1] TRUE
> 1 != 2
[1] TRUE
> 1 < 2
[1] TRUE
> 1 <= 1
[1] TRUE
> 1 > 0
[1] TRUE
> 1 >= -9
[1] TRUE
> all.equal(1.0, 1.0)
[1] TRUE
> all.equal(1.0, 1.1)
[1] "Mean relative difference: 0.1"
```

----

**SLIDE: EXERCISE 01**

![images/red_green_sticky.png](images/red_green_sticky.png)

----

**SLIDE: Variables**

* **VARIABLES** are critical to programming in general, and also to working in `R`
* Variables are like **NAMED BOXES**
    * Like a box, they **HOLD THINGS**
    * When we make reference to a box's name, we **MEAN THE THING THE BOX CONTAINS**
* Here, the box is called `Name`, and it contains the word `Samia`
* When we refer to the box, we call it `Name`, and we might ask questions like:
    * "What is the length of `Name`?", meaning "What is the length of the word in the box called `Name`?" (answer: 5)

----

**SLIDE: Variables - Interactive Demo**

* This is a very important concept, so we're going to go through some practical examples, to reinforce it
    * In `R`, variables are assigned with the **ASSIGNMENT OPERATOR** `<-`
    * We will assign the value `1/40` to the variable `x`
    * **DEMO CODE**

```R
> x <- 1 / 40
```

* At first, nothing seems to happen, but we can see that the variable `x` now exists, and contains the value `0.025` - a **DECIMAL APPROXMATION** of the fraction `1/40`

```R
> x
[1] 0.025
```

* **CLICK ON THE ENVIRONMENT WINDOW**
    * You should see that `x` is defined, there
* The *Environment* window in `RStudio` tells you the name and content of every variable currently active in your `R` session.

* This **VARIABLE CAN BE USED ANYWHERE THAT EXPECTS A NUMBER**
    * such as an argument to a function

```R
> log(x)
[1] -3.688879
> sin(x)
[1] 0.0249974
> x + x
[1] 0.05
> 2 * x
[1] 0.05
> x ^ 2
[1] 0.000625
```

* We can **REASSIGN VALUES TO VARIABLES**
    * **MONITOR THE VALUE OF `x` IN THE ENVIRONMENT WINDOW**
    * We can also assign a variable to itself, to modify the variable

```R
> x <- 100
> x <- x + 5
```

* We can assign **ANY KIND OF VALUE** to a variable
    * Including **STRINGS** - i.e. sets of characters

```R
> name <- "Samia"
> name
[1] "Samia"
```

* But **BE CAREFUL** - `R` is not always intuitive
    * Strings in particular may not work the way you expect

```R
> length(name)
[1] 1
> nchar(name)
[1] 5
```

----

**SLIDE: Removing Variables**

* To remove **ONE OR MORE SPECIFIED VARIABLES**, use `rm()`
    * **`ls()` IS A FUNCTION THAT LISTS VARIABLES** (like the Environment tab) 
    * **DEMO CODE**

```R
> x <- 1
> y <- 2
> z <- 3
> ls()
[1] "x" "y" "z"
> rm(x)
> ls()
[1] "y" "z"
> rm(y, z)
> ls()
character(0)
```



----

**SLIDE: EXERCISE 02**

Solution:

`mass <- 47.5`
This will give a value of 47.5 for the variable mass

`age <- 122`
This will give a value of 122 for the variable age

`mass <- mass * 2.3`
This will multiply the existing value of 47.5 by 2.3 to give a new value of 109.25 to the variable mass.

`age <- age - 20`
This will subtract 20 from the existing value of 122 to give a new value of 102 to the variable age.

----

**SLIDE: Good Project Management Practices**

* There is **NO SINGLE GOOD WAY TO ORGANISE A PROJECT**
    * It's important to find something that **WORKS FOR YOU**
    * But it's **ALSO IMPORTANT THAT IT WORKS FOR COLLABORATORS**
    * Some **PRINCIPLES MAKE THINGS EASIER FOR EVERYONE**

* Using a **SINGLE WORKING DIRECTORY PER PROJECT/ANALYSIS**
    * **EASY TO PACKAGE UP** the whole directory and move it around, or share it
    * **NO NEED TO HUNT AROUND THE WHOLE DISK** to find relevant or important files.
    * You can use **RELATIVE PATHS** that will always work, so long as you work within the project directory
* Treat your **RAW DATA AS READ-ONLY**
    * Establishes **PROVENANCE** and **ENABLES REANALYSIS**
    * Keep in **SEPARATE SUBFOLDER**
* **CLEAN THE DATA PROGRAMMATICALLY** (part of the analysis chain)
    * Remove/fill in null values, etc. - whatever is appropriate
    * **KEEP CLEANED DATA SEPARATE FROM RAW** - like food hygiene
* **GENERATED OUTPUT IS DISPOSABLE**
    * This means **ANYTHING GENERATED AUTOMATICALLY BY YOUR CODE/ANALYSIS**
    * If a file can be generated by scripts/code in your project, no need to put it under version control

----

**SLIDE: Example Directory Structure**

* This is **ONE WAY TO STRUCTURE YOUR WORKING DIRECTORY**
    * It's a good starting point, but something else might be more appropriate for your own work

* **`WORKING DIR/`** is the *root* directory of the project.
    * Everything related to the project (subdirectories of data, scripts and figures; `git` files; configuration files; notes to yourself; whatever)
* **`data/`** is a subdirectory for storing data
    * raw data only, or raw and intermediate data? **YOUR DECISION**
    * `data/raw`, `data/intermediate` - **USE SUBFOLDERS WHEN SENSIBLE**
* **`data_output/`** could be a place to write the analysis output (`.csv` files etc.)
* **`documents/`** is a place where notes, drafts, and explanatory text could be stored
* **`fig_output/`** could be a place to write graphical output of the analysis (keep separate from tables)
* **`scripts`** might be where you would choose to keep executable code that automates your analysis

* The important thing is that the structure is **SELF-EXPLANATORY WHERE POSSIBLE**