# dynamuscript-template


I recently set out to write an entire manuscript for a scientific publication in R. As with any endeavor that invovles gaining new coding skills, I knew the process would be slow at first but rewarding in the long run. It certainly was both, but now that I have seen the result I will definitely be writing all manuscrupts in the future in this way. After overcoming the initial learning curve, I am convinced that writing in this way not only increases the reproducibility of my science but is also faster and way more fun. 

This repository is where I will keep a template that will serve as a starting point for other dyanmic manuscript (dynamuscript) writing projects. The workflow and organization reflect an emphasis on simplicity, reproducibility, and scalability. 

The *Data* folder contains all raw data used in the study.

The *Manuscript* folder contains the _manuscript.rmd_ file which has all code for analyses and creation of figures and tables, and is used to build the manuscript with this line in R.
`knitr::knit("Manuscript/manuscript.Rmd")`

This folder also contains the output files in _.pdf_ and _.tex_ formats. The _.bib_ file contains all references.

The *Figures* folder contains all figures produced by _manuscript.rmd_.

## Thoughts

I chose to use the R package _papaja_ as a starting point because the dfault output looks really nice and requires litle changes for my needs. 

