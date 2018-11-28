---
title             : "The title"
shorttitle        : "Title"

author: 
  - name          : "First Author"
    affiliation   : "1"
    corresponding : yes    # Define only one corresponding author
    address       : "Postal address"
    email         : "my@email.com"
  - name          : "Second Author"
    affiliation   : "1,2"

affiliation:
  - id            : "1"
    institution   : "School 1"
  - id            : "2"
    institution   : "Institute B"

abstract: |
  
  
keywords          : "keywords"
wordcount         : "X"

bibliography      : ["r-references.bib"]

floatsintext      : no
figurelist        : no
tablelist         : no
footnotelist      : no
linenumbers       : yes
mask              : no
draft             : no
figsintext        : yes

documentclass     : "apa6"
classoption       : "man"
output            : papaja::apa6_pdf

header-includes   : 
  \newcommand{\beginsupplement}{\setcounter{table}{0}  \renewcommand{\thetable}{S\arabic{table}} \setcounter{figure}{0} \renewcommand{\thefigure}{S\arabic{figure}}}
---




```r
iris_data<-read.csv("../Data/iris_data.csv")
```


```r
sepalcor<-cor.test(iris_data$Sepal.Length, iris_data$Sepal.Width)
petalcor<-cor.test(iris_data$Petal.Length, iris_data$Petal.Width)

speciesmeanstable<-iris_data %>% 
  group_by(Species) %>%
  summarise(Sepal.Length=mean(Sepal.Length), Sepal.Width=mean(Sepal.Width), Petal.Length=mean(Petal.Length), Petal.Width=mean(Petal.Width))
```


```r
pdf("../Figures/iriscorrelationsplot.pdf", width=5, height=5)

sepals<-ggplot(iris_data, aes(x= Sepal.Length, y=Sepal.Width, col=Species))+
  geom_point()+
  theme_classic()

petals<-ggplot(iris_data, aes(x= Petal.Length, y=Petal.Width, col=Species))+
  geom_point()+
  theme_classic()

cowplot::plot_grid(sepals, petals, ncol=1, labels="auto")

dev.off()
```

# Introduction
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam a magna ac lorem aliquet pellentesque et bibendum diam. Phasellus in lectus malesuada, consequat arcu quis, dignissim massa. Donec laoreet egestas leo, et tristique tortor cursus at. Aenean non molestie orci, sit amet bibendum sem. Sed convallis vulputate tortor quis sagittis. Aliquam placerat lacus at urna sodales, id facilisis libero fringilla. Quisque ac orci id ex fermentum euismod. Pellentesque tempor, urna vel sollicitudin mollis, purus ex ornare eros, sed suscipit orci enim sed sem. Mauris quis purus ut purus congue tincidunt. Suspendisse potenti. Maecenas mauris velit, imperdiet nec feugiat ut, eleifend a urna. Vestibulum arcu lacus, suscipit eu tincidunt et, sodales eget lectus. Donec sit amet accumsan est.

Vivamus ligula urna, scelerisque nec sem sit amet, condimentum pharetra magna. Nullam tincidunt ipsum ut dolor rutrum, ac malesuada eros blandit. Vestibulum consectetur ultricies lectus, quis cursus risus fermentum sed. Proin non nunc eget sem commodo faucibus et sed ex. Ut in orci lorem. Morbi vehicula, lorem vitae fermentum egestas, odio felis rutrum nisi, nec mattis elit nisl vel libero. Vivamus facilisis nisi id mauris lobortis, ut egestas massa tristique. Nam ac massa facilisis, molestie arcu ut, finibus tellus.

Sed sagittis velit ac nisi egestas, a maximus lorem congue. Nulla sodales laoreet tortor eleifend congue. Aliquam et felis vehicula, condimentum mauris non, varius purus. Nunc ligula ex, volutpat interdum interdum sed, porta ut eros. Duis molestie, turpis sed aliquam rhoncus, orci dui lacinia mauris, ut feugiat mauris leo at enim. Mauris non tortor eleifend, vulputate justo sit amet, ullamcorper risus. Vestibulum in odio sed erat venenatis imperdiet ac at massa.

# Materials and Methods
## Data
## Analyses
We used R for all analyses [@R-base].

# Results

(ref:iriscorrelationsplot) Sepals and petals in three _Iris_ species. (a) Relationship between sepal length and width. (b) Relatiopnship between petal length and width.  



```r
knitr::include_graphics("../Figures/iriscorrelationsplot.pdf", dpi = 108)
```

<embed src="../Figures/iriscorrelationsplot.pdf" title="(ref:iriscorrelationsplot)" alt="(ref:iriscorrelationsplot)" width="\textwidth" type="application/pdf" />


\begin{table}[tbp]
\begin{center}
\begin{threeparttable}
\caption{\label{tab:speciesmeanstable}Mean values for floral organ traits in three Iris species.}
\small{
\begin{tabular}{lllll}
\toprule
Species & \multicolumn{1}{c}{Sepal.Length} & \multicolumn{1}{c}{Sepal.Width} & \multicolumn{1}{c}{Petal.Length} & \multicolumn{1}{c}{Petal.Width}\\
\midrule
setosa & 5.006 & 3.428 & 1.462 & 0.246\\
versicolor & 5.936 & 2.770 & 4.260 & 1.326\\
virginica & 6.588 & 2.974 & 5.552 & 2.026\\
\bottomrule
\end{tabular}
}
\end{threeparttable}
\end{center}
\end{table}

Length and width of sepals were not correlated (r = -0.1175698, p = 0.1518983, Figure \@ref(fig:iriscorrelationsplot)a). In contrast, length and width of petals showed a strong positive correlation (r = 0.9628654, p = 4.6750039 &times; 10<sup>-86</sup>, figure \@ref(fig:iriscorrelationsplot)b).

The mean species values for each trait are shown in table \@ref(tab:speciesmeanstable)



# Discussion


\newpage

# References

```r
r_refs(file = "r-references.bib")
```

\begingroup
\setlength{\parindent}{-0.5in}
\setlength{\leftskip}{0.5in}

<div id = "refs"></div>
\endgroup

\newpage
\beginsupplement

# Supplement 

## Software used
We used R [Version 3.5.1; @R-base] and the R-packages *cowplot* [Version 0.9.3; @R-cowplot], *dplyr* [Version 0.7.8; @R-dplyr], *forcats* [Version 0.3.0; @R-forcats], *ggplot2* [Version 3.1.0; @R-ggplot2], *papaja* [Version 0.1.0.9842; @R-papaja], *purrr* [Version 0.2.5; @R-purrr], *readr* [Version 1.2.1; @R-readr], *stringr* [Version 1.3.1; @R-stringr], *tibble* [Version 1.4.2; @R-tibble], *tidyr* [Version 0.8.2; @R-tidyr], and *tidyverse* [Version 1.2.1; @R-tidyverse] for all our analyses.

