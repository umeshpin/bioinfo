# R for Bionformatics 


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
