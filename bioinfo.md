# R for Bionformatics 
Data
https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic
or https://drive.google.com/drive/u/0/folders/1P0871RmvCYoec5i7xmU3vyrjuD8OKbb3

Using this dataset of 32 variables measuring the size and shape of cell nuclei, goal is to create a model that will allow us to predict whether a breast cancer cell is benign or malignant.
Data set description
Features are computed from a digitized image of a fine needle aspirate (FNA) of a breast mass. They describe characteristics of the cell nuclei present in the image. Our dataset consists of 569 observations and 32 variables. There is an ID variable, a diagnosis variable revealing if they were benign or malignant, and 30 measurement variables detailing the size and shape of the cell nuclei. The diagnosis, a categorical variable, is our response variable and the 30 measurement variables, all of which are continuous, are our potential explanatory variables for our model. The 30 measurement variables are actually only 10 different features of the nucleus, but with 3 different measurements of each; the mean, the standard error and the ‘worst’ or largest (mean of the three largest values). The 10 features included are:
radius - mean of distances from center to points on the perimeter
texture - standard deviation of gray-scale values
perimeter
area
smoothness - local variation in radius lengths
compactness - perimeter^2 / area - 1.0
concavity - severity of concave portions of the contour
concave points - number of concave portions of the contour
symmetry
fractal dimension - “coastline approximation” - 1
First let us do some exploratory analysis

Lets load the data
```
bcdata <- read.csv("~/Desktop/TKM/bcdata.csv")
Let us explore the data
head(bcdata)
names(bcdata)
dim(bcdata)
str(bcdata)
summary(bcdata)
ncol(bcdata)
nrow(bcdata)
To find the null
is.na(bcdata)
```

#to find columns which is null
```
colnames(bcdata)[ apply(bcdata, 2, anyNA) ]
```
To take specific column from a data
```
bcdata[1]
```
In R, "-1" is used extensively
```
dim(bcdata)
dim(bcdata[-1])
str(bcdata[-1])
names(bcdata[-1])
```
Convert values into 0 and 1
```
diagnosis <- as.numeric(bcdata$diagnosis == "M")
wbcd$diagnosis <- factor(ifelse(wbcd$diagnosis=="B","Benign","Malignant"))
```
To remove first columns
```
bcdata <- bcdata[,-c(1:2)]
```
Missing value treatment
Here you make some modification to the document and check the code
```
bcdata$f[is.na(bcdata$f)] <- mean(bcdata$f, na.rm = T)
```
We can covert the total set into test and train very easily
```
bcdata <- read.csv("~/Desktop/TKM/bcdata.csv")
trainindex<-createDataPartition(bcdata$diagnosis,p=0.8,list=FALSE)
train<-bcdata[trainindex,] 
test<-bcdata[-trainindex,]
```

```install packages
 install.packages("rentrez")
```

```import sequence
dengueseq_fasta <- rentrez::entrez_fetch(db = "nucleotide", 
                          id = "NC_001477", 
                          rettype = "fasta")
```
```fasta                          
dengueseq_fasta
```
```count char 
nchar(dengueseq_fasta)
```
Trim sting 

```Trim sting 
strtrim(dengueseq_fasta, 100)
```

```Biostrings 
library(Biostrings)
```
DNA as string
```DNA
DNAString("ATCGTTCGCTGCTG")
```Biostrings 

```Pattren 
dna1 <- DNAString("ATCGCTTTCGA")
matchPattern("CG", dna1, fixed = TRUE)
```


# Lets Do in cloud  :cloud: :cloud: :cloud:

Login to 
https://rstudio.cloud/
