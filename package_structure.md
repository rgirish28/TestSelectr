Package Notes
=============


### Prerequisites
- Install R package dependencies by running ```install.packages(c("devtools", "roxygen2", "testthat", "knitr"))```
- Command line tools and XCode for OSX (Applicable to both of us)
- Prerequisites for Linux and Windows:
  - Linux: Along with R installation, install r-base-dev package by running ```sudo apt-get install r-base-dev```
  - Windows: Install [RTools](http://cran.r-project.org/bin/windows/Rtools/)
- Run following code to check whether installation is correct:
```
library(devtools)
has_devel()
```
### Optional for C++ development
- Install CLion for OSX (Makes C++ development much easier)

### Name
- Change name to testselectr. Use all lower letters/capital letters to avoid ambiguity.

### Package Structure
- Run ```devtools::create("path/to/package/pkgname")``` or use wizard for package creation/initialisation
- Each package has three basic components:
  - R/ directory
  - A basic DESCRIPTION file
  - A basic NAMESPACE file
- Also contains pkgname.RProj for RStudio integration

### Package lifecycle
- **Source**: All source(R,c++,description, etc) files 
- **Bundle/Bundled package**: Single file containing all source files. ```.tar.gz``` is the standard, which means it is a ```.tar``` archive that has been compressive using ```gzip```. Useful for sharing code, but not much else. Use ```.Rbuildignore``` to prevent certain source files from being included in the bundle. Built using ```devtools::build()```.
- **Binary**: Useful for distributing package to user who does not have dev tools installed. Different binaries are built for different distributions(Windows,Mac,Linux). Built using ```devtools::build(binary = TRUE)```. 
![Files present in source, bundle and binary versions](http://r-pkgs.had.co.nz/diagrams/package-files.png)
- **Installed**: Package installed into R framework. Can be installed in different ways. Usually installed from source using ```devtools::install()```. ```R CMD INSTALL``` is the command line tool that actually installs the package, which devtools acts as a wrapper around. 
![Different ways of installing packages](http://r-pkgs.had.co.nz/diagrams/installation.png)
- **In memory**: Package loaded into memory usually using ```library(pkgname)```. Other ways of loading pkgs from source into memory. Not important at the moment.

**Library** is just a collection of packages, usually a directory containing them. 

