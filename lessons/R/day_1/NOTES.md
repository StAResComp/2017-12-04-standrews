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

## SECTION 01: Introduction to `R` and `RStudio`

**SLIDE: Learning Objectives**

* We need to get some **FAMILIARITY WITH OUR WORKING ENVIRONMENT**: the `RStudio` IDE
* We'll **BUILD UPON THE `GIT` LESSON** because `RStudio` integrates naturally with `git` to keep all your analysis and code under version control.
* We'll introduce `R` syntax, and **SEE HOW `R` REPRESENTS DATA** and how to **PROGRAM IN `R`**
* If we have time we'll deal with **MANAGING SOME OF THE MANY USEFUL PACKAGES** available in `R`

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
* But **`R` HAS ADVANTAGES FOR REPRODUCIBLE ANALYSIS**

* Perhaps the key thing is that it **SEPARATES DATA FROM ANALYSIS**.
    * In `R`, when you do things to the original data, unless you overwrite the file, that original data remains unmodified.
    * In `Excel`, it's easy to overwrite data with copy-and-paste (and many bad things have happened as a result)

* Because **YOUR ANALYSIS IN `R` IS A PROGRAM**, every step is written down explicitly, and understandable.
    * In `Excel`, there is no clear record of where you moved your mouse, or what you copied and pasted, and it's not immediately obvious how your formulas work.

* `R` code is **EASY TO SHARE AND ADAPT**, and to apply again to a different or a modified input dataset.
* `R` code can also be **RUN ON EXTREMELY LARGE DATASETS**, quickly. That's much harder in `Excel`.

----

**SLIDE: What is `RStudio`?**

* `RStudio` is an **INTEGRATED DEVELOPMENT ENVIRONMENT** - which is to say it's a very powerful tool for writing and using `R` and programs in the `R` language.

* On the left is the `RStudio` IDE **WHILE I WAS WRITING THIS PRESENTATION IN IT** on a Mac
* On the right is the Windows version, with an example analysis and visualisation

* You can use it to **INTERACT WITH `R` DIRECTLY TO EXPERIMENT WITH DATA**
* It has a **CODE/SCRIPT EDITOR FOR WRITING PROGRAMS**
* It has tools for **VISUALISING DATA**
* It has built-in **GIT INTEGRATION FOR MANAGING YOUR PROJECTS**