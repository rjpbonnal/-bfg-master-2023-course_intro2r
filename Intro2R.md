% Introduction to R
% Raoul Jean Pierre Bonnal
% 2023-03-27

# Synopsis

---

* R’s History
* Introduction to R and RStudio
* Project Management With RStudio
* Seeking Help
* Data Structures (basic)

# What is R?

---

R is a programming language for statistical computing and graphics
supported by the R Core Team and the R Foundation for Statistical
Computing.

---

R is used among data miners, bioinformaticians and statisticians for data analysis and developing statistical software.

___
Users have created packages to augment the functions of the R language.

---

R is one of the most commonly used programming languages in data mining

---

As of December 2022, R ranks 11th in the TIOBE index, a measure of programming language popularity, in which the language peaked in 8th place in August 2020.

---

The official R software environment is an open-source free software environment within the GNU package, available under the GNU General Public License. 

---

It is written primarily in C, Fortran, and R itself (partially self-hosting). Precompiled executables are provided for various operating systems. 

# History 

## History

R was started by professors __Ross Ihaka__ and __Robert Gentleman__ as a programming language to teach introductory statistics at the University of Auckland.

## History

The name of the language comes from the shared first letter of the
authors, Ross and Robert.

## History

* In Aug 1993 first shared binaries of R on the data archive StatLib and the s-news mailing list
* In Jun 1995, R free and open-source under the GNU GPL
* In Apr 1997 Mailing lists for the R project
* In Dec 1997 R officially became a GNU project
* In 1997 The R Core Team was formed
* In Feb 2000 The first official 1.0 version
* In Apr 2003 the R Foundation as a non-profit org

# R

## The project
https://www.r-project.org/
![R home](images/r-home.png){width=50%}

## The network

__CRAN__ is a network of ftp and web servers around the world that store identical, up-to-date, versions of code and documentation for R. Please use the CRAN mirror nearest to you to minimize network load. ~90 and growing…

## CRAN
The Comprehensive R Archive Network (CRAN) was founded in 1997 by Kurt
Hornik and Fritz Leisch to host R's source code, executable files,
documentation, and user-created packages.

## CRAN
Its name and scope mimics the Comprehensive TeX Archive Network and
the Comprehensive Perl Archive Network.

## CRAN

CRAN originally had three mirrors and 12 contributed packages.
As of December 2022, it has 103 mirrors and 18,976 contributed
packages.

## CRAN
https://cran.r-project.org/
![R CRAN](images/r-cran.png){width=60%}

## Interfaces

![](images/r-environments.png)

R has a CLI. Multiple third-party GUI: RStudio, an IDE, and Jupyter, a notebook interface.


# SetUp

## Install R
in your Almalinux 9 update the available system packages:

```bash
sudo dnf update
```

## Install R
Once the update is completed, enable the EPEL and CRB on AlmaLinux 9.
```bash
sudo dnf install epel-release
sudo dnf config-manager --set-enabled crb
```

## Install R

```bash
sudo dnf install R
```
Type `Y` when required.

## Install R
Check the version

```bash
$ R --version
R version 4.1.3 (2022-03-10) -- "One Push-Up"
Copyright (C) 2022 The R Foundation for Statistical Computing
Platform: x86_64-redhat-linux-gnu (64-bit)

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under the terms of the
GNU General Public License versions 2 or 3.
For more information about these matters see
https://www.gnu.org/licenses/.
```

## Run R
```bash
$ R
R version 4.1.3 (2022-03-10) -- "One Push-Up"
Copyright (C) 2022 The R Foundation for Statistical Computing
Platform: x86_64-redhat-linux-gnu (64-bit)
R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under certain conditions.
Type 'license()' or 'licence()' for distribution details.
  Natural language support but running in an English locale
R is a collaborative project with many contributors.
Type 'contributors()' for more information and
'citation()' on how to cite R or R packages in publications.
Type 'demo()' for some demos, 'help()' for on-line help, or
'help.start()' for an HTML browser interface to help.
Type 'q()' to quit R.
> 
```

## Install RStudio
[Download
RStudio](https://posit.co/download/rstudio-desktop/#download) for
Microsoft Windows

Running the RStudio under WSL2 can be a kind of *experience*

# Intro to  RStudio

## Run RStudio

Open RStudio from Microsoft Windows

---

![](images/r-rstudio.png){width=70%}

[swcarpentry](https://swcarpentry.github.io/r-novice-gapminder/01-rstudio-intro/index.html)

---

![](images/r-rstudio-script.png){width=70%}

## Run some code

click on the *Run* button above the editor panel, or select *Run
Lines* from the *Code* menu, or hit *Ctrl+Return* in Windows or
Linuxor *⌘+Return* on macOS.

![](images/r-rstudio-run.png)

# Project Management With R-Studio

---

[swcarpentry](https://swcarpentry.github.io/r-novice-gapminder/02-project-intro/index.html)
with rstudio

---

A good project layout will ultimately make your life easier:

* It will help ensure the integrity of your data;
* It makes it simpler to share your code with someone else (a lab-mate, collaborator, or supervisor);
* It allows you to easily upload your code with your manuscript submission;
* It makes it easier to pick the project back up after a break.

---

RStudio has the ability to create *Projects* which is self-contained
and this helps in mitigating the reproducibility problem.

---

To create a project in RStudio:

1. Click the “File” menu button, then “New Project”
2. Click “New Directory”
3. Click “New Project”
4. Type in the name of the directory to store your project, e.g. “my_project”
5. If available, select the checkbox for “Create a git repository.”
6. Click the “Create Project” button

---

That will create a *.Rproj* file in the directory of your choice. 

Double clicking on the file name RStudio will open and eventually
recovering the previous session.

---

How to recover from a previous session R uses the *.RData* which saves
the current workspace in the current working directory.

```R
save.image(file="my_workspace.RData")
```

```R
load("my_workspace.RData")
```

---

```R
save.image()
```

Creates by default a *.RData* file, an hidden file.

---

# Suggestions

---

* Treat data as read only
* Data Cleaning
* Treat generated output as disposable
* Separate function definition and application
* Save the data in the data directory
* Working directory
* Version control

## Treat Data as read only

---

Do not use a live dataset/file as input for your work.
It may change overtime and others can corrupt your "schema"

## Data Cleaning and Wrangling

---

Data can be dirty and in a wrong format.

*Cleaning* Check that data are correct, consistent

*Wrangling*  Tranform data from one format to the other. Also known as
*Data Munging*.

---

You can accomplish to this with R, the Shell, other languages, whaever
you want but you MUST track the steps with *code*.

YOUR MEMORY CAN FAIL

## Treat generated output as disposable

---

Anything generated by your scripts should be treated as disposable

* output folder w/subfolder for different analyses
* results for final output

it should all be able to be regenerated from your scripts.

## Separate function definition and application

---

Save your code into:

* *lib* for storing R functions
* *src*/*scripts* for R workflows
* *bin* for R executables or other software

## Save the data in the data directory

---

you can dowload the data from the web browser, the `wget`, `curl`,
from withing R with
```R
url<-"https://raw.githubusercontent.com/swcarpentry/r-novice-gapminder/gh-pages/_episodes_rmd/data/gapminder_data.csv"
destfile<-"./gapminder_data.csv"
download.file(url, destfile)
```

## Working directory

---

If you use *.Rproj* R sets automatically the working directory to
where your project is located.

Otherwise, remember to set it manually

---

Check the current working directory
```R
getwd()
```

Set the workging directory
```R
setwd("directory_path")
```

## Version control

In the future ;)

## Scaffold

* *data* for the input
* *bin* for external software
* *doc* for documentation
* *lib* for the funtions your wrote to better organize the code
* *src* for your `.R` scripts
* *output* for the intermediate results
* *results* for the final results

# Seeking Help

---

[swcarpentry](https://swcarpentry.github.io/r-novice-gapminder/03-seeking-help/index.html)

---

```R
?function_name
help(function_name)
```

---

Each help page is broken down into sections:

* Description: An extended description
* Usage: The arguments and their default values
* Arguments: argument is expecting
* Details: Any important details to be aware of
* Value: The data the function returns
* See Also: Any useful related functions
* Examples: How to use the function

---

Notice how related functions might call for the same help file:
```R
?write.table()
?write.csv()
```

---

*vignette* is an extended documentations with tutorials and examples

---

```R
vignette()
```
![](images/r-vignette.png){width=60%}

---

```R
vignette(package="package-name")
```
Open a PDF

---

Fuzzy search 

```R
??function_name
```

---

```R
??set
```

![](images/r-help-fuzzyserach.png){width=60%}

# Data Structures (basic)

---

[swcarpentry1](http://swcarpentry.github.io/r-novice-inflammation/13-supp-data-structures/index.html)
[swcarpentry2](https://swcarpentry.github.io/r-novice-gapminder/04-data-structures-part1/index.html)

  thanks to swcarpentry.github.io

# Packages/Libraries

---

Every programming language:

* tries to keep the core as simple as possible.
* can be extended with functionalities that are not available in the core language.

---

Do you remmeber [CRAN](https://cran.r-project.org/web/packages/available_packages_by_name.html)?

![](images/r-cran-packages.png)

---

![](images/r-cran-package-a3.png){width=60%}

---

```R
> install.packages("A3")
Installing package into ‘/Users/rbonnal/Library/R/4.0/library’
(as ‘lib’ is unspecified)
--- Please select a CRAN mirror for use in this session ---
```

this is under macOS

---

```R
> install.packages("A3")
Installing package into ‘/Users/rbonnal/Library/R/4.0/library’
(as ‘lib’ is unspecified)
--- Please select a CRAN mirror for use in this session ---
```

R will download automatically all the dependencies.

---

*RTF* 
```R
> ?install.packages
```

---

![](images/r-manual.png){width=45%}

---

![](images/r-manual-details.png){width=70%}
