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
    * **NOTE:** when comparing numbers, it's better to use `all.equal()` (*machine numeric tolerance*) **ASK IF THERE'S ANYONE FROM MATHS/PHYSICS**

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
> all.equal(pi-1e-7, pi)
[1] "Mean relative difference: 3.183099e-08"
> all.equal(pi-1e-8, pi)
[1] TRUE
> pi-1e-8 == pi
[1] FALSE
```

----

**SLIDE: Challenge 01**

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

**SLIDE: Challenge 02**

Solution:

`mass <- 47.5`
This will give a value of 47.5 for the variable mass

`age <- 122`
This will give a value of 122 for the variable age

`mass <- mass * 2.3`
This will multiply the existing value of 47.5 by 2.3 to give a new value of 109.25 to the variable mass.

`age <- age - 20`
This will subtract 20 from the existing value of 122 to give a new value of 102 to the variable age.

![images/red_green_sticky.png](images/red_green_sticky.png)

----

**SLIDE: Good Project Management Practices**

* There is **NO SINGLE GOOD WAY TO ORGANISE A PROJECT**
    * It's important to find something that **WORKS FOR YOU**
    * But it's **ALSO IMPORTANT THAT IT WORKS FOR COLLABORATORS**
    * Some **PRINCIPLES MAKE THINGS EASIER FOR EVERYONE**

* Using a **SINGLE WORKING DIRECTORY PER PROJECT/ANALYSIS**
    * **NAME IT AFTER THE PROJECT**
    * **EASY TO PACKAGE UP** the whole directory and move it around, or share it - **OR PUBLISH ALONGSIDE YOUR PAPER**
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

----

**SLIDE: Project Management in `RStudio`**

* `RStudio` **TRIES TO BE HELPFUL** and provides the 'Project' concept
    * Keeps **ALL PROJECT FILES IN A SINGLE DIRECTORY**
    * **INTEGRATES WITH `GIT`**
    * Enables switching between projects within `RStudio`
    * Keeps project histories

* **INTERACTIVE DEMO**

* **CREATE PROJECT**
* Click `File` -> `New Project`
    * Options for how we want to create a project: brand new in a new working directory; turn an existing directory into a project; or checkout a project from `GitHub` or some other repository
* Click `New Directory`
    * Options for various things we can do in `RStudio`. Here we want `New Project`
* Click `New Project`
    * We are asked for a directory name. **ENTER `swc-r-lesson`**
    * We are asked for a parent directory. **PUT YOURS ON THE DESKTOP; STUDENTS CAN CHOOSE ANYWHERE SENSIBLE**
    * **SELECT `Create a git repository`** - this will create and initialise a `git` repository, just for this project
* Click `Create Project`
* **YOU SHOULD SEE AN EMPTY-ISH `RSTUDIO` WINDOW**

* **INSPECT PROJECT ENVIRONMENT**
* First, **NOTE THE WINDOWS**: editor; environment; files
* **EDITOR** is empty
* **ENVIRONMENT** is empty
* **FILES** shows
    * **CURRENT WORKING DIRECTORY** (see breadcrumb trail)
    * **TWO FILES**: `*.Rproj` - information about your project; `.gitignore` - your project's `.gitignore` file (remember the `git` lesson?)
* **CLICK ON `GIT` TAB**
    * We see that the files are not yet added to the project (status is `?`)
    * **CHECK BOXES TO STAGE FILES**
    * **CLICK ON `DIFF` TO SEE CHANGES** (note colours, lines, etc.)
    * **CLICK ON `COMMIT` TO COMMIT CHANGES**
    * **WRITE COMMIT MESSAGE** (add .gitignore and R project files to repo)
    * **CLICK `COMMIT`** (explain message)

* **CREATE DIRECTORIES IN PROJECT**
* **Create directoris called `scripts` and `data`**
    * Click on `New Folder`
    * Enter directory name (`scripts`)
    * Note that the directory now exists in the `Files` tab (but not in the `git` tab, as the directory is empty)
    * Do the same for `data/`
* **NOTE THAT WE WILL NOW POPULATE THE DIRECTORY**

----

**SLIDE: Working in RStudio**

* `RStudio` offers **SEVERAL WAYS TO WRITE CODE**
    * We'll not see all of them today
    * You've seen **DIRECT INTERACTION IN THE CONSOLE** (entering variables)
    * `RStudio` also has an editor for writing scripts, notebooks, markdown documents, and Shiny applications (**EXPLAIN BRIEFLY**)
    * It can also be used to write plain text

* **INTERACTIVE DEMO OF `R` SCRIPT**

* Click on `File` -> `New File` -> `Text File`. **NOTE THAT THE EDITOR WINDOW OPENS**
* Enter the following text, and **EXPLAIN CSV**
    * plain text file
    * one row per line
    * column entries separated by commas
    * first row is header data
    * **NEEDS A BLANK LINE AT THE END**
    * **DATA DESCRIBES CATS**

```
coat,weight,likes_string
calico,2.1,1
black,5.0,0
tabby,3.2,1

```

* **SAVE THE FILE AS `data/feline_data.csv`**
    * Click on disk icon
    * Navigate to `data/` subdirectory
    * Enter filename `feline_data.csv`
* **NOTE CHANGES IN `GIT` TAB**
    * The `data` directory appears!
    * Click on `Staged` and **THE FILE APPEARS**
    * Click `Commit` and add a commit string, e.g. "add cat dataset"
* **CLOSE THE EDITOR FOR THAT FILE**

* Click on `File` -> `New File` -> `R Script`.
* **EXPLAIN COMMENTS** while entering the code below
    * **COMMENTS ANNOTATE YOUR CODE**: reminders for you, and information for others
* **EXPLAIN `read.csv()`**
    * `read.csv()` is a **FUNCTION** that reads data from a **CSV-FORMAT FILE** into a variable in `R`
 
```R
# Script for exploring data structures

# Load cat data as a dataframe
cats <- read.csv(file = "data/feline_data.csv")
```

* **SAVE THE SCRIPT**
   * Click on `File` -> `Save`
   * Navigate to the `scripts/` subdirectory
   * Enter filename `data_structures` (**EXTENSION IS AUTOMATICALLY APPLIED**)
**NOTE CHANGES IN `GIT` TAB**
   * The `scripts` directory appears!
   * Click on `Staged` and the file appears
   * Click on `Commit` and add a commit string, e.g. "add data structures script"
* **DO YOU SEE THE VARIABLE IN THE ENVIRONMENT?**
   * **NO** - because the code hasn't been executed, only written.

* **RUN THE SCRIPT**
   * Click on `Source` and **NOTE THIS RUNS THE WHOLE SCRIPT**
* Go to the `Environment` tab
   * **NOTE THE DATA WAS LOADED IN THE VARIABLE `cats`**
   * Note that there is a description of the data (3 obs. of 3 variables)
   * **CLICK ON THE VARIABLE AND NOTE THAT THE TABLE IS NOW VISIBLE** - this is helpful
   * **YOU CANNOT EDIT THE DATA IN THIS TABLE** - you can sort and filter, but not modify the data. This **ENFORCES GOOD PRACTICE** (compare to Excel).

----

**SLIDE: 03. A First Analysis in `RStudio`**

----

**SLIDE: Learning Objectives**

* We're going to cover some ways of loading data into an `R` project/analysis
* We'll **EXPLORE SOME FUNCTIONS FOR SUMMARISING DATA**
* Sometimes we want to use only a portion of our data, and we'll see some **WAYS OF INDEXING DATASETS**
* We'll also look at some ways to **PLOT DATA IN R**, using the built-in *base graphics*

----

**SLIDE: Our Task**

* We've got some medical data relating to a new treatment for arthritis
* There are some measurements of patient inflammation, taken over a period of days post-treatment for each patient
* We've been **ASKED TO PRODUCE A SUMMARY AND SOME GRAPHS**

* **DOWNLOAD THE FILE FROM THE LINK TO `data/`**
* **EXPLAIN THE LINK IS ON THE ETHERPAD PAGE** (no need to type!)
* **DEMO THIS**
    * **NOTE:** A new directory is created *within* `data`, called `data`. **THIS IS UNTIDY, SO LET'S CLEAN**
    * **COPY ALL FILES BEGINNING WITH `inflammation` TO THE PARENT FOLDER**
    * **THEN DELETE THE SUBFOLDER AND ZIP FILE**
    * **ADD THE DATA FILES TO THE REPO** (can shift-click, here)

* **CHECK EVERYONE'S READY TO PROCEED**

---- 

**SLIDE: Loading Data - Interactive Demo**

* We've already created some cat data manually, but **THIS IS UNUSUAL** - most data comes in the form of plain text files

**START DEMO**
* **INSPECT DATA IN FILES WINDOW**
    * Click on filename, and select `View File`
    * Note: **THERE IS NO HEADER** and **THERE ARE NO ROW NAMES**
    * Ask: **IS THIS WELL-FORMATTED DATA?**
    * I happen to know that there is **one row per patient, and the columns are days, in turn, post-treatment**, and **measurements are inflammation levels**
* **WHAT IS THE DATA TYPE**
    * Tabular, with **EACH COLUMN SEPARATED BY A COMMA**, so **CSV**
    * **IN THE CONSOLE** use `read.csv()` to read the data in
    * Note: **IF WE DON'T ASSIGN THE RESULT TO A VARIABLE WE JUST SEE THE DATA**
* **CREATE A NEW SCRIPT**
    * Click the **triangle next to the new document icon**
    * Add the code and **SAVE AS `scripts/inflammation`** (`RStudio` adds the extension)
    * See that the file appears in `Files` and `Git` windows

```R
# Preliminary analysis of inflammation in arthritis patients

# Load data (no headers, CSV)
data <- read.csv(file = "data/inflammation-01.csv", header = FALSE)
```

* **INSPECT THE DATA**
    * `Source` the script
    * Check the `Environment` window: 60 observations (patients) of 40 variables (days)
    * **CLICK ON `data`**
    * **COLUMN HEADERS ARE PROVIDED: `Vn`** for *variable n*
    * `dim()` - *dimensions* of data: rows X columns
    * `length()` - number of columns in the table
    * `ncol()` - number of columns in the table
    * `nrow()` - number of rows in the table

```R
> head(data, n = 2)
  V1 V2 V3 V4 V5 V6 V7 V8 V9 V10 V11 V12 V13 V14 V15 V16 V17 V18 V19 V20 V21 V22 V23 V24 V25 V26
1  0  0  1  3  1  2  4  7  8   3   3   3  10   5   7   4   7   7  12  18   6  13  11  11   7   7
2  0  1  2  1  2  1  3  2  2   6  10  11   5   9   4   4   7  16   8   6  18   4  12   5  12   7
  V27 V28 V29 V30 V31 V32 V33 V34 V35 V36 V37 V38 V39 V40
1   4   6   8   8   4   4   5   7   3   4   2   3   0   0
2  11   5  11   3   3   5   4   4   5   5   1   1   0   1
> dim(data)
[1] 60 40
> length(data)
[1] 40
> ncol(data)
[1] 40
> nrow(data)
[1] 60
```
	
----

**SLIDE: Challenge 03**

**SOLUTION**

```R
read.csv(file='file.csv', sep=';', dec=',')
```

![images/red_green_sticky.png](images/red_green_sticky.png)

----

**SLIDE: Indexing Data**

* We can refer to an element in our dataset by *indexing* it
    * We **LOCATE A SINGLE ELEMENT as `[row, column]` in square brackets**

```R
> ncol(data)
[1] 40
> data[1,1]
[1] 0
> data[50,1]
[1] 0
> data[50,20]
[1] 16
> data[30,20]
[1] 16
```

* To get a **RANGE OF VALUES**, use the `:` separator to mean 'to':

```R
> data[1:4, 1:4]   # rows 1 to 4; columns 1 to 4
  V1 V2 V3 V4
1  0  0  1  3
2  0  1  2  1
3  0  1  1  3
4  0  0  2  0
> data[30:32, 20:22]
   V20 V21 V22
30  16  14  15
31  16  13   7
32   9  19  15
```

* To get a **WHOLE ROW OR COLUMN**, leave that entry blank

```R
> data[5,]
  V1 V2 V3 V4 V5 V6 V7 V8 V9 V10 V11 V12 V13 V14 V15 V16 V17 V18 V19 V20 V21 V22 V23 V24 V25 V26
5  0  1  1  3  3  1  3  5  2   4   4   7   6   5   3  10   8  10   6  17   9  14   9   7  13   9
  V27 V28 V29 V30 V31 V32 V33 V34 V35 V36 V37 V38 V39 V40
5  12   6   7   7   9   6   3   2   2   4   2   0   1   1
> data[,16]
 [1]  4  4 15  8 10 15 13  9 11  6  3  8 12  3  5 10 11  4 11 13 15  5 14 13  4  9 13  6  7  6 14
[32]  3 15  4 15 11  7 10 15  6  5  6 15 11 15  6 11 15 14  4 10 15 11  6 13  8  4 13 12  9
```

----

**SLIDE: Summary Functions - Interactive Demo**

* **`R` was designed for data analysis**, so has many built-in functions for analysing and describing data
    * **TALK THROUGH CODE IN CONSOLE**

```R
> max(data)
[1] 20
> max(data[2,])
[1] 18
> max(data[,7])
[1] 6
> min(data[,7])
[1] 1
> mean(data[,7])
[1] 3.8
> median(data[,7])
[1] 4
> sd(data[,7])
[1] 1.725187
```

----

**SLIDE: Challenge 04**

```R
> animal <- c('m', 'o', 'n', 'k', 'e', 'y')
> animal[1:3]
[1] "m" "o" "n"
> animal[4:6]
[1] "k" "e" "y"
> animal[3:1]
[1] "n" "o" "m"
> animal[-1]
[1] "o" "n" "k" "e" "y"
> animal[-4]
[1] "m" "o" "n" "e" "y"
> animal[-1:-4]
[1] "e" "y"
> animal[-1:4]
Error in animal[-1:4] : only 0's may be mixed with negative subscripts
```

![images/red_green_sticky.png](images/red_green_sticky.png)

----

**SLIDE: Repetitive Calculations - Interactive Demo**

* We might want to **CALCULATE MEAN INFLAMMATION FOR EACH PATIENT**, but doing it the way we've just seen is tedious and slow.
* Happily **COMPUTERS WERE INVENTED TO SAVE US THE HASSLE**
* We could automate this task in any of several ways available in `R`
    * What we'd like to do is **APPLY A FUNCTION TO EACH ROW**
    * `R` has an `apply()` function exactly for this
    * **IN THE CONSOLE**

```R
> apply(X = data, MARGIN = 1, FUN = mean)
 [1] 5.450 5.425 6.100 5.900 5.550 6.225 5.975 6.650 6.625 6.525 6.775 5.800 6.225 5.750 5.225
[16] 6.300 6.550 5.700 5.850 6.550 5.775 5.825 6.175 6.100 5.800 6.425 6.050 6.025 6.175 6.550
[31] 6.175 6.350 6.725 6.125 7.075 5.725 5.925 6.150 6.075 5.750 5.975 5.725 6.300 5.900 6.750
[46] 5.925 7.225 6.150 5.950 6.275 5.700 6.100 6.825 5.975 6.725 5.700 6.250 6.400 7.050 5.900
```

* **IN OUR ANALYSIS SCRIPT** we want to assign these values to a variable, and **ALSO CALCULATE AVERAGE BY DAY**
    * So long as we provide arguments in the correct order, **WE DON'T NEED TO PROVIDE ARGUMENT NAMES** - true for most `R` functions

```R
# Calculate average inflammation by patient and day
avg_inflammation_patient <- apply(X = data, MARGIN = 1, FUN = mean)
avg_inflammation_day <- apply(data, 2, mean)
```

* **RUN THE LINES**
    * Note that the values appear in the Environment tab
* Like many common operations, there's an `R` function that's a shortcut
    * **IN THE CONSOLE**

```R
> rowMeans(data)
 [1] 5.450 5.425 6.100 5.900 5.550 6.225 5.975 6.650 6.625 6.525 6.775 5.800 6.225 5.750 5.225
[16] 6.300 6.550 5.700 5.850 6.550 5.775 5.825 6.175 6.100 5.800 6.425 6.050 6.025 6.175 6.550
[31] 6.175 6.350 6.725 6.125 7.075 5.725 5.925 6.150 6.075 5.750 5.975 5.725 6.300 5.900 6.750
[46] 5.925 7.225 6.150 5.950 6.275 5.700 6.100 6.825 5.975 6.725 5.700 6.250 6.400 7.050 5.900
> colMeans(data)
        V1         V2         V3         V4         V5         V6         V7         V8         V9 
 0.0000000  0.4500000  1.1166667  1.7500000  2.4333333  3.1500000  3.8000000  3.8833333  5.2333333 
       V10        V11        V12        V13        V14        V15        V16        V17        V18 
 5.5166667  5.9500000  5.9000000  8.3500000  7.7333333  8.3666667  9.5000000  9.5833333 10.6333333 
       V19        V20        V21        V22        V23        V24        V25        V26        V27 
11.5666667 12.3500000 13.2500000 11.9666667 11.0333333 10.1666667 10.0000000  8.6666667  9.1500000 
       V28        V29        V30        V31        V32        V33        V34        V35        V36 
 7.2500000  7.3333333  6.5833333  6.0666667  5.9500000  5.1166667  3.6000000  3.3000000  3.5666667 
       V37        V38        V39        V40 
 2.4833333  1.5000000  1.1333333  0.5666667 
```

----

**SLIDE: Base Graphics**

* We're doing all this work to try to **GAIN INSIGHT INTO OUR DATA**
* **VISUALISATION IS A KEY ROUTE TO INSIGHT**

* `R` has many graphics packages - some of which produce extremely beautiful images, or are tailored to a specific problem domain
* The built-in graphics are known as *base graphics*
* They may not be as pretty, or as immediately suited for all circumstances as some other packages, but they are still very powerful

----

**SLIDE: Plotting - Interactive Demo**

* **IN THE SCRIPT**
    * `R`'s **`plot()` FUNCTION IS GENERAL AND WORKS FOR MANY KINDS OF DATA**
    * **RUN EACH LINE IN TURN**
    * **NOTE WHERE PLOTS SHOW** (Plot window)
    * Opportunity to note: **VARIABLES HELP READABILITY**
    * **USE ARROW BUTTONS** to cycle through plots
    * **COMMIT CHANGES WHEN DONE**

```R
# Plot data summaries
# Average inflammation by patient
plot(avg_inflammation_patient)

# Average inflammation per day
plot(avg_inflammation_day)

# Maximum inflammation per day
max_inflammation_day <- apply(data, 2, max)
plot(max_inflammation_day)

# Minimum inflammation per day
plot(apply(data, 2, min))

# Show a historgram of average patient inflammation
hist(avg_inflammation_patient)
```

* **THE `hist()` FUNCTION PLOTS A HISTOGRAM OF INPUT DATA FREQUENCY/COUNT**
    * The choice of bin sizes/*breaks* could be improved
    * We need to **PROVIDE THE BOUNDARIES BETWEEN BINS**
    * **IN THE CONSOLE**

```R
hist(avg_inflammation_patient, breaks=c(5, 6, 7, 8))
```

* We'd have to **TYPE IN A LOT OF NUMBERS** to get smaller breaks, which is **SLOW**
    * The `seq()` function generates a sequence of numbers for us

```R
> seq(5, 8)
[1] 5 6 7 8
> hist(avg_inflammation_patient, breaks=seq(5, 8))
```

* We can **SET THE INTERVAL OF THE SEQUENCE**

```R
> seq(5, 8, by=0.2)
 [1] 5.0 5.2 5.4 5.6 5.8 6.0 6.2 6.4 6.6 6.8 7.0 7.2 7.4 7.6 7.8 8.0
> hist(avg_inflammation_patient, breaks=seq(5, 8, by=0.2))
``` 

* **IN THE SCRIPT**
    * Add a line with the histogram for average patient inflammation

```R
# Show a historgram of average patient inflammation
hist(avg_inflammation_patient, breaks=seq(5, 8, by=0.2))
```

* **IN THE SCRIPT**
   * Demonstrate changing the input file
   * **CHANGING FILENAME IN A SCRIPT IS QUICKER THAN RETYPING ALL THE COMMANDS**

----

**SLIDE: Challenge 05**

```R
# Plot standard deviation by day
plot(apply(data, 2, sd))
```

![images/red_green_sticky.png](images/red_green_sticky.png)

----

**SLIDE: 04. Data Structures in `R`**

----

**SLIDE: Learning Objectives**

* In this section, you'll be learning about the data types in `R`: **WHAT DATA IS**
* You'll also be learning about the data *structures*: **WHAT DATA IS BUILT INTO - HOW IT IS ARRANGED**
* And you'll also learn how to find out what type/structure a particular piece of data has
* Putting it together, you'll see how `R`'s data types and structures relate to the types of data that you work with, yourself.

----

**SLIDE: Data Types and Structures in `R`**

* `R` is **MOSTLY USED FOR DATA ANALYSIS**
* `R` is set up with key, core data types designed to help you work with your own data
* A lot of the time, `R` focuses on tabular data (like our cat example)
* **INTERACTIVE DEMO**

* **SWITCH TO THE CONSOLE** (Establish that `cats` is available as a variable)
* If you type `cats`, you get a nice tabular representation of your data 

```R
> cats
    coat weight likes_string
1 calico    2.1            1
2  black    5.0            0
3  tabby    3.2            1
```

* **THINK ABOUT THE DATA TYPES** Are they all the same?
    * **NO** `coat` is text; `weight` is some real value (in kg or pounds, maybe), and `likes_string` looks like it should be `TRUE`/`FALSE`
    * **DOES IT MAKE SENSE TO WORK WITH THEM AS IF THEY'RE THE SAME THING?** (No)

* **EXTRACT A COLUMN FROM A TABLE**
   * Use `$` notation in the console
   * **NOTE THE AUTOCOMPLETION**

```R
> cats$weight
[1] 2.1 5.0 3.2
```

* **WHAT DID `R` RETURN?**
    * A *vector* (1D ordered collection) of numbers
* **WE CAN OPERATE ON THESE *VECTORS* **
    * *Vectors* are an important concept, and `R` is largely built so that operations on vectors are central to data analysis.

```R
> cats$weight + 2
[1] 4.1 7.0 5.2
```

* **WHAT ABOUT OTHER COLUMNS?**

```R
> cats$coat
[1] calico black  tabby 
Levels: black calico tabby
```

* **WHAT DID `R` RETURN?**
    * A *vector* of *levels*
    * We'll talk about these in more detail shortly, but the key point is that `R` **DOESN'T THINK THEY'RE ONLY WORDS** - it **THINKS THEY'RE NAMED CATEGORIES OF OBJECT**. `R` is assuming that you mean to import *data*
    * We can operate on this vector, too (**EXPLAIN `paste()`**)

```R
> paste("My cat is", cats$coat)
[1] "My cat is calico" "My cat is black"  "My cat is tabby" 
```

* **WHAT HAPPENS NEXT?**

```R
> cats$weight + cats$coat
[1] NA NA NA
Warning message:
In Ops.factor(cats$weight, cats$coat) : ‘+’ not meaningful for factors
```

* You probably already realised that wasn't going to work, because adding "calico" to "2.1" is nonsense.
* **THESE DATA TYPES ARE NOT COMPATIBLE** for addition
* `R`'s data types reflect the ways in which data is expected to interact
* **UNDERSTANDING HOW YOUR DATA MAP TO `R`'s DATA TYPES IS KEY**
   * It's very important to understand how `R` sees your data (you want `R` to see your data the same way you do)
   * Many problems in `R` come down to incompatibilities between data and data types.

----

**SLIDE: What Data Types Do You Expect?**

* **ASK THE STUDENTS**
    * What data types would you expect to see?
    * What data types do you think you would **WANT OR NEED**, from your own experience?
* **SPEND A COUPLE OF MINUTES ON THIS**
    * The difference between a *data type* and a *data structure*

----

**SLIDE: Data Types in `R`**

* `R`'s data *types* are *atomic*: they are **FUNDAMENTAL AND EVERYTHING ELSE IS BUILT UP FROM THEM**, like matter is built up from atoms
    * In particular, all the data *structures* are built up from data *types*
* There are only **FIVE DATA TYPES** in `R` (though one is split into two…)
    * **logical**: Boolean, True/False (also `1`/`0`)
    * **numeric**: anything that's a number on the number line; two types of number are supported: `integer` and `double` (real)
    * **complex**: complex numbers, defined on the 2D plane
    * **character**: text data - readable symbols
    * **raw**: binary data (we'll not be dealing with this)

* **LET'S LEARN A BIT MORE ABOUT THEM IN THE DEMO**
* **ENTER DEFINITIONS INTO THE SCRIPT**
    * Covering the major data types

```R
# Some variables of several data types
truth <- TRUE
lie <- FALSE
i <- 3L
d <- 3.0
c <- 3 + 0i
txt <- "TRUE"
```

* **EXECUTE THE VARIABLE DEFINITIONS**
    * Select the definition lines
    * Click on `Run`
    * **OBSERVE THAT THE LINES ARE RUN IN THE CONSOLE**
    * **OBSERVE THAT THE VALUES ARE DEFINED IN THE ENVIRONMENT**
    * Note the difference between `Data` and `Values` in the environment
    * Note that the script is updated in the `Git` tab: commit the change

* **USE `typeof()` TO FIND THE TYPE OF A VARIABLE**

```R
> typeof(i)
[1] "integer"
> typeof(c)
[1] "complex"
> typeof(d)
[1] "double"
```

* **TO TEST IF A DATA ITEM HAS A TYPE, USE `is.<type>()`**

```R
> is.numeric(3)
[1] TRUE
> is.numeric(d)
[1] TRUE
> is.double(i)
[1] FALSE
> is.integer(d)
[1] FALSE
> is.numeric(txt)
[1] FALSE
> is.character(txt)
[1] TRUE
> is.character(truth)
[1] FALSE
> is.logical(truth)
[1] TRUE
```

* **THE INTEGER, COMPLEX, AND DOUBLE ARE EQUAL** even if they're not the same data type
    * numbers are comparable, regardless of data type

```R
> i == c
[1] TRUE
> i == d
[1] TRUE
> d == c
[1] TRUE
```

* **INTEGER, COMPLEX AND DOUBLE ARE NOT ALL `numeric`** though

```R
> is.numeric(i)
[1] TRUE
> is.numeric(c)
[1] FALSE
```

----

**SLIDE: Challenge 06**

* Let the students work for a couple of minutes, then demonstrate.

![images/red_green_sticky.png](images/red_green_sticky.png)

----

**SLIDE: FIVE COMMON `R` DATA STRUCTURES**

* These are perhaps the five data types you'll come across most often in `R`
* We'll deal with them through examples
* **INTERACTIVE DEMO IN SCRIPT**

* **VECTORS**
    * These are the **MOST COMMON DATA STRUCTURE**
    * Vectors can contain **ONLY A SINGLE DATA TYPE** (*atomic vectors*)
    * **ADD CODE TO SCRIPT** then use `Run` to run in console
    * To create a vector **USE THE `c()` FUNCTION** (`c()` is `combine`; use `?c`)
    * First we define an **ATOMIC VECTOR OF NUMBERS** - each element is an integer

```R
# Define an integer vector
x <- c(10, 12, 45, 33)
```

* We can use some `R` functions to find out more about this variable
    * **RUN CODE IN CONSOLE**

```R
> length(x)
[1] 4
> typeof(x)
[1] "double"
> str(x)
 num [1:4] 10 12 45 33
``` 

* The `str()` function **REPORTS THE STRUCTURE OF A VARIABLE**
    * Here, `num` means 'numeric'; `[1:4]` means there are four elements; the elements are listed
    * **NOTE THAT THIS INFORMATION IS IN THE ENVIRONMENT TAB**
    
* **DEFINE A SECOND VECTOR IN THE SCRIPT**

```R
# Define a vector
xx <- c(1, 2, 'a')
```

* In the Environment tab, you can see **THIS IS A CHARACTER VECTOR**

```R
> length(xx)
[1] 3
> typeof(xx)
[1] "character"
> str(xx)
 chr [1:3] "1" "2" "a"
``` 

* **IS THE TYPE OF THE VECTOR WHAT YOU EXPECTED?**
    * This is one of the things that trips people up with `R` - they think their data is of one type, but `R` thinks it makes more sense to have it as another type

----

**SLIDE: Challenge 07**

* Let the students work for a couple of minutes, then demonstrate.

![images/red_green_sticky.png](images/red_green_sticky.png)

----

**SLIDE: Coercion**

* *Coercion* is what happens when you **COVERT ONE DATA TYPE INTO ANOTHER**
* If `R` thinks it needs to, it will **COERCE DATA IMPLICITLY** without telling you
* There is a set order for coercion
    * `logical` can be coerced to `integer`, but `integer` cannot be coerced to `logical`
    * That's because `integer` can describe all `logical` values, but not *vice versa*
    * Everything can be represented as a `character`, so that's the fallback position for `R`
* **IF THERE'S A FORMATTING PROBLEM IN YOUR DATA, `R` MIGHT CONVERT THE TYPE TO COPE**
    * `R` will choose the simplest data type that can represent all items in the vector

* **INTERACTIVE DEMO IN CONSOLE** More useful things to do with vectors
* You can (usually) **COERCE VECTORS MANUALLY** with `as.<type>()`

```R
> as.character(x)
[1] "10" "12" "45" "33"
> as.complex(x)
[1] 10+0i 12+0i 45+0i 33+0i
> as.logical(x)
[1] TRUE TRUE TRUE TRUE
> xx
[1] "1" "2" "a"
> as.numeric(xx)
[1]  1  2 NA
Warning message:
NAs introduced by coercion 
> as.logical(xx)
[1] NA NA NA
```

* You can generate **NUMBER SEQUENCES** as vectors
    * The `seq()` function returns a vector
    * As does the `:` operator

```R
> seq(10)
 [1]  1  2  3  4  5  6  7  8  9 10
> seq(1, 10)
 [1]  1  2  3  4  5  6  7  8  9 10
> seq(35, 40, by=0.5)
 [1] 35.0 35.5 36.0 36.5 37.0 37.5 38.0 38.5 39.0 39.5 40.0
> 1:10
 [1]  1  2  3  4  5  6  7  8  9 10
> 5:8
[1] 5 6 7 8 
```

* You can **APPEND ELEMENTS TO A VECTOR WITH `c()`**

```R
> x
[1] 10 12 45 33
> c(x, 57)
[1] 10 12 45 33 57
> x
[1] 10 12 45 33
> x <- c(x, 57)
> x
[1] 10 12 45 33 57
```

* There are useful **FUNCTIONS TO GET INFORMATION ABOUT A VECTOR**

```R
> x <- 0:10
> tail(x)
[1]  5  6  7  8  9 10
> head(x)
[1] 0 1 2 3 4 5
> head(x, n=2)
[1] 0 1
```

* You can **GIVE VECTOR ELEMENTS NAMES**
    * They're then referred to as *named vectors*

```R
> x <- 1:4
> names(x)
NULL
> str(x)
 int [1:4] 1 2 3 4
> names(x) <- c("a", "b", "c", "d")
> x
a b c d 
1 2 3 4 
> str(x)
 Named int [1:4] 1 2 3 4
 - attr(*, "names")= chr [1:4] "a" "b" "c" "d"
```