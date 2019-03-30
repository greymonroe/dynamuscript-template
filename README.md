# Template for creating a dynamic manuscript

## Folders
### Data/
The *Data* folder contains all raw data used in the study. My philosophy for data is one inspired by the sterile technique of microbiologists. If you open a data file in a program like excel, you expose it to contamination (ie. unknowingly changing values and saving the file). It's best to obtain these data files once, for example after an experiment or downloaded from public resource and do all analyses, recalculations, sorting, etc in a program like R. You can save the output, but never change the original data.

### src/
Contains scripts or other code that will be called from _manuscript.rmd_. Useful for long code. Also includes a _Sandbox.R_ file for development.

### RData/
Countains RData objects that are products of scripts and code. These serve as intemediates between Data and final Figures and Tables that will not end up in the final manuscript but are necessary for analyses. Primarily this is useful when generating these data objects is slow and creating them everytime the manuscript is compiled takes a long. You can load these rather than regenerate them everytime.

### Figures/
The *Figures* folder contains all figures produced by _manuscript.rmd_. I prefer to produce figures in _.pdf_ format.

### Tables/
The _Tables_ folder has all tables created by _manuscript.rmd_. These are tables that will be submitted with your manuscrupt for publication, not tables of data used for analyses.

### Manuscript/
The *Manuscript* folder contains the _manuscript.rmd_ file which has all code for analyses and creation of figures and tables, citations, and of course the wirtten content of the paper. This is the main file you will work with and is used to build the manuscript with this line in R. Open _manuscript.rmd_ in RStudio and use the "Knit" button to build your manuscript.

This folder will also contain the output manuscript files in _.pdf_ and _.tex_ formats created when you build (Knit) your manuscript. 

The _.bib_ file in this fodler contains all references.

## Details

I chose to use the R package _papaja_ because the default output looks really nice and required litle changes for my needs. I've added some Latex code to the header so that tables and figures in the Supplement section are named accordingly.

For data wrangling, I've finally learned to appreciate _tidyverse_ whcih is a nice alternative to the data wrangling approaches of times past. For making plots I prefer to use _ggplot2_ for it's versatility. To combine mutliple plots, I use _cowplots_ because I like the label parameter which automatically adds _a, b, c, ect_ if there are mutltiple plots combined.

This is a work in progress, and probably always will be. Your feedback is valuble and if you have or find a better way to do this, please share. Please post to the issues page of this github repo. 



