# Milestone2

The data that is to be analysed was loaded into the R-notebook. 
To do so, the first 20 files under the two subsets being tested were downloaded and stored locally. I renamed my files when downloading to the format: File No. 1 under the male category - "M1.tsv"

First, the required libraries were loaded into the notebook. 

```{r}
library(edgeR)
library(limma)
library(glimma)
```
To access the data, the files must be saved in the current working directory. 
I have set my working directory to "/Users/ramiyasivakumar/", using the setwd() command then returned the current working directory to the screen using "getwd()". 

```{r}
setwd("/Users/ramiyasivakumar/")
getwd()
```

All of the files containing the gene counts data were then collectively stored in a location called "files"

```{r}
files <- c("M1.tsv","M2.tsv","M3.tsv","M4.tsv","M5.tsv","M6.tsv","M7.tsv","M8.tsv","M9.tsv","M10.tsv","M11.tsv","M12.tsv","M13.tsv","M14.tsv","M15.tsv","M16.tsv","M17.tsv","M18.tsv","M19.tsv","M20.tsv","F1.tsv","F2.tsv","F3.tsv","F4.tsv","F5.tsv","F6.tsv","F7.tsv","F8.tsv","F9.tsv","F10.tsv","F11.tsv","F12.tsv","F13.tsv","F14.tsv","F15.tsv","F16.tsv","F17.tsv","F18.tsv","F19.tsv","F20.tsv")
```
A new Value in the environment is formed as a results. 
The values of each file are read and the first 5 rows of the dataframe are displayed. As the data does not contain a header line, it is specified as "FALSE". 

```{r}
read.delim(files[1],nrow=5,header=FALSE)
```
The reaDGE function allows for a dataframe containing all of the files to be created. 
```{r}
x <- readDGE(files, columns=c(1,2))
class(x)
dim(x)
```
The dataframe that is formed contains the ENSEMBL Gene IDs as rows and the filenames as column headers. The data represents the number of gene counts of each file. 
A new dataframe is introduced to the environment as a result. 
dim(x) returns the number of genes found in each file and the number of files present. 

