---
output:
  html_document: default
  pdf_document: default
---
# **BCB546X_R_Assignment**
## Data Import
Used the readr "read_tsv" function (tab delimited .txt files) to read the files from BCB546X Git repository using URL for the raw file.

```{r data_import}
library(tidyverse)
Fang <- read_tsv("https://raw.githubusercontent.com/EEOB-BioData/BCB546X-Fall2018/master/assignments/UNIX_Assignment/fang_et_al_genotypes.txt")
SNP_Position <- read_tsv("https://raw.githubusercontent.com/EEOB-BioData/BCB546X-Fall2018/master/assignments/UNIX_Assignment/snp_position.txt")
```

## Data Inspection
Inspected type, size and length of the data frame from the grid view of RStudio environment panel. Also used the ncol(), nrow(), and dim() functions with data frames.

```{r data_inspection}
ncol(Fang)
nrow(Fang)
dim(Fang)
str(Fang)
ncol(SNP_Position)
nrow(SNP_Position)
dim(SNP_Position)
str(SNP_Position)
```

## Data Processing
Extracted and subset data for Maize and Teosinte groups from the Fang genotypes file using the which() function and logical operator "==".

```{r data_subsetting}
Fang_maize <- Fang[which(Fang$Group=="ZMMIL" | Fang$Group =="ZMMLR" | Fang$Group == "ZMMMR"),]
Fang_teosinte <-Fang[which(Fang$Group=="ZMPBA" | Fang$Group =="ZMPIL" | Fang$Group == "ZMPJA"),]
#### Inspected the files
head(Fang_maize)
head(Fang_teosinte)
```



