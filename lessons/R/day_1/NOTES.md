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
* We'll **BUILD UPON THE `GIT` LESSON** because `RStudio` integrates naturally with `git` to keep all your analysis and code under version control.
* We'll introduce `R` syntax, and **SEE HOW `R` REPRESENTS DATA** and how to **PROGRAM IN `R`**
* If we have time we'll deal with **MANAGING SOME OF THE MANY USEFUL PACKAGES** available in `R`

----

**SLIDE: `RStudio` Overview - Live Demo**