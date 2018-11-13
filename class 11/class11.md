Stuctural Bioinformatics Class 11
================
Diego Quintero

PDB database composition statistics
-----------------------------------

Download PDB stats as a CSV file from: <http://www.rcsb.org/stats/summary>

``` r
pdbstats <- read.csv("Data Export Summary.csv", row.names =1)
```

Let's look at table

``` r
library(knitr)
```

    ## Warning: package 'knitr' was built under R version 3.5.1

``` r
kable(pdbstats)
```

|                        |  Proteins|  Nucleic.Acids|  Protein.NA.Complex|  Other|   Total|
|------------------------|---------:|--------------:|-------------------:|------:|-------:|
| X-Ray                  |    122263|           1960|                6333|     10|  130566|
| NMR                    |     10898|           1263|                 253|      8|   12422|
| Electron Microscopy    |      1822|             31|                 657|      0|    2510|
| Other                  |       244|              4|                   6|     13|     267|
| Multi Method           |       119|              5|                   2|      1|     127|
| Total number of struct |      ures|               |                    |       |        |

``` r
#total number of entries
nstru <- sum(pdbstats[,5])

#percentage of X-Ray structures
perXray <- pdbstats["X-Ray", "Total"]/nstru
perXray <- round(perXray*100,2)

#percentage of Electron Microscopy
perElecMic <- pdbstats["Electron Microscopy","Total"]/nstru
perElecMic <- round(perElecMic*100,2)
```

A1. There are 89.49% X-ray structures and 1.72% Electorn Microsopy structures in the PDB database as of 2018-11-06 10:22:23

Calculating the percentage of proteins

``` r
numProt <- sum(pdbstats$Proteins)/nstru

numProt <- round(numProt*100,2)
```

Total percent of Proteins is 92.77%
