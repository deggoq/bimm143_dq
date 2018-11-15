Class 14
================
Diego Quintero

Import Asthma data from csv

``` r
asthmaData <- read.csv("373531-SampleGenotypes-Homo_sapiens_Variation_Sample_rs8067378.csv")
```

``` r
TotalGenotypes <- nrow(asthmaData)

num_AA <- asthmaData$Genotype..forward.strand. == 'A|A'

num_AA = sum(num_AA)
```

``` r
prop_AA <- num_AA/TotalGenotypes*100

prop_AA <- round(prop_AA,2)
```

There are 34.38% "A|A" genotypes out of 64
