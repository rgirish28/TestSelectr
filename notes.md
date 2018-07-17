Notes
=====

### Immediate to-do
- Deep scan of CRAN for any similar packages
- Deep scan of github for any similar packages (note that packages can be published on Github and downloaded with the devtools package)

### To-do
- Draft conceptual workflow for package
- Find supporting literature/evidence-base for decision process (i.e., deep scan/review of literature)
- Draft pseudo functions
- Read [R Packages](http://r-pkgs.had.co.nz/)

### Functionality
- Optimise with c++ via [Rcpp](http://www.rcpp.org/). Also see [here](http://adv-r.had.co.nz/Rcpp.html)
- The primary function (i.e., decision process) could work via decision tree. The structure of dataframe objects can be assesed to determine: (i) the no. of predictor and criterion variables; (ii) the structure of each variable (i.e., continuous/discrete); (iii) the levels of the variables (if applicable); (iv) which test assumptions have been met (e.g., normality, homoscedasticity, etc.); (v) if NA's exist in the data (some tests require no NA values). Arguments could be passed to the function to help further in the selection process (e.g., if the data is a nested data structure, nested = FALSE; whether the user wants to investigate differences/relationships, method = c(differences, relationships, predictions)). The structure of time series data needs consideration - could a tidy format solve this (in terms of all columns being one variable).
- In order to preserve dataframe objects for later analysis, a function that supplies a vector of labels for each variable can be supplied which can be passed into the primary selector function. This will tell selectr which variables are IV's and which are DV's.
- Maintain a 'tidy' approach inline with the tidyverse suite of packages.
- limit to inferential statistics?
- there is already a package on CRAN called selectr. Rename (selector? Tselect? Test Selectr?)
- Include transformr. Check for normality across variables using skenwss and kurtosis z-scores etc. If the variable is not normal, iterate through a list of transformations (e.g., log, square, exponential), at each stage assessing normality, then if any transformations return a normal distribution (and transformed variable), select the most normal. Should this take part in a separate pre-cursor function or be integrated with the main select function? 
- Should other assumption tests be in their own function (e.g., assumptions())?
- argument to main function called outliers = c(method 1, method 2, etc.). Provide different methods for removing outliers supported by the lit. Use Cook's distance etc. to determin outliers.