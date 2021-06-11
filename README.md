# Covid_C1_shinyapp
This app explores multi-omics dataset for severe/moderate covid-19 cases and allows the users to upload their own dataset for prediction.
Run the app locally in Rstudio on laptop by

``` r
library(shiny)
library(shinydashboard)
library(ggplot2)
library(limma)
library(DT)
library(tidyverse)
library(plotly)
library(vroom)
library(HiDimDA)
library(e1071)
library(randomForest)
library(dplyr)
library(stringr)
library(tools)

runUSYDGithub <- function (repo, username = getOption("github.user"), ref = "master", 
          subdir = NULL, destdir = NULL, ...) 
{
  if (grepl("/", repo)) {
    res <- strsplit(repo, "/")[[1]]
    if (length(res) != 2) 
      stop("'repo' must be of the form 'username/repo'")
    username <- res[1]
    repo <- res[2]
  }
  url <- paste("https://github.sydney.edu.au/", username, "/", repo, 
               "/archive/", ref, ".tar.gz", sep = "")
  runUrl(url, subdir = subdir, destdir = destdir, ...)
}

runUSYDGithub(
  repo = "Covid_C1_shinyapp", 
  username = "YYAO3610", 
  ref = "main")
```

The demo_uploading_file folder contains 2 different demo uploading file using the test set from Su et al/Shen et al. You can use these files as testing uploading files. pdata,mdata,rdata refer to proteomics,metabolomics,transcriptomics respectively.
