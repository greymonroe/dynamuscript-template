# Template for creating a dynamic manuscript

### Grey Monroe

Perhaps it was reviewer #3 who requested a small change to the analyses which would only change the result slightly but required you recreate every figure and update all the stats in your paper. Or maybe it was dragging that figure into Word and watching hours of work formatting the document dissappear before you eyes. Whatever the reasons, you're here because you know there has to be a better way. 

![](https://i.kym-cdn.com/photos/images/original/000/809/345/144.jpg "True")

The writing process has always been linked to technology. When was the scientific paper written on a typewriter? A generation ago most papers used simple analyses and contained just a few figures, sometimes drafted by hand. If this were still the case, Microsoft Word would still be a suitable tool for writing scientific papers, but of course this is a far cry from the modern manuscript and its 20 supplemental figures. Managing all of this requires a better system of creating manuscripts, one that makes publishing science faster and more flexible.

For these reasons, I recently set out to write an entire manuscript for a scientific publication in R. As with any endeavor that invovles gaining new coding skills, I knew the process would be slow at first but rewarding in the long run. It certainly was both, but now that I have seen the result I will definitely be writing all manuscrupts in the future in this way. After overcoming the initial learning curve, I am convinced that writing like this not only increases the reproducibility of my science but is also faster and way more fun. 

This repository is where I will keep a template that will serve as a starting point for other dyanmic manuscript (dynamuscript) writing projects. The workflow and organization reflect an emphasis on simplicity, reproducibility, and scalability. 

## Folders
### Data/
The *Data* folder contains all raw data used in the study. My philosophy for data is one inspired by the sterile technique of microbiologists. If you open a data file in a program like excel, you expose it to contamination (ie. unknowingly changing values and saving the file). It's best to obtain these data files once, for example after an experiment or downloaded from public resource and do all analyses, recalculations, sorting, etc in a program like R. You can save the output, but never change the original data.

### Figures/
The *Figures* folder contains all figures produced by _manuscript.rmd_. I prefer to produce figures in _.pdf_ format.

### Tables/
The _Tables_ folder has all tables created by _manuscript.rmd_. These are tables that will be submitted with your manuscrupt for publication, not tables of data used for analyses.

### Manuscript/
The *Manuscript* folder contains the _manuscript.rmd_ file which has all code for analyses and creation of figures and tables, citations, and of course the wirtten content of the paper. This is the main file you will work with and is used to build the manuscript with this line in R.
`knitr::knit("Manuscript/manuscript.Rmd")` Alternatively, you can open _manuscript.rmd_ in RStudio and use the "Knit" button to build your manuscript.

This folder will also contain the output manuscript files in _.pdf_ and _.tex_ formats created when you build (Knit) your manuscript. 

The _.bib_ file in this fodler contains all references.

## Details

I chose to use the R package _papaja_ because the dfault output looks really nice and requires litle changes for my needs. I've added some Latex code to the header so that tables and figures in the Supplement section are named accordingly.

For data wrangling, I've finally learned to appreciate _tidyverse_ whcih is a nice alternative to the data wrangling approaches of times past. For making plots I prefer to use _ggplot2_ for it's versatility. To combine mutliple plots, I use _cowplots_ because I like the label parameter which automatically adds _a, b, c, ect_ if there are mutltiple plots combined.

This is a work in progress, and probably always will be. Your feedback is valuble to all of us, and if you have or find a better way to do this, please share. Please post to the issues page of this github repo. 



