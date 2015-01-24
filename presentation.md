Presentation
========================================================
author: Developing Data Products Student 
date: Sat Jan 24 14:54:31 2015

Exploring Motor Trend Car Road Tests
========================================================

In this presentation, I will explore mtcars (Motor Tend Car Road Tesets) data. The data was extracted from the 1974 Motor Trend US magazine, and comprises fuel consumption and 10 aspects of automobile design and performance for 32 automobiles (1973–74 models).

The mtcars data exploration includes the following steps:

- Load the data and check number of variables and number of observations
- Convert variables into appropriate data type and produce summary statistics
- Explor the data using plots

Load the data
========================================================
In this step, I load the data and explor the content of the data like number of variables and number of observations, variable names, and variable types.


```r
    library(datasets)
    str(mtcars)
```

```
'data.frame':	32 obs. of  11 variables:
 $ mpg : num  21 21 22.8 21.4 18.7 18.1 14.3 24.4 22.8 19.2 ...
 $ cyl : num  6 6 4 6 8 6 8 4 4 6 ...
 $ disp: num  160 160 108 258 360 ...
 $ hp  : num  110 110 93 110 175 105 245 62 95 123 ...
 $ drat: num  3.9 3.9 3.85 3.08 3.15 2.76 3.21 3.69 3.92 3.92 ...
 $ wt  : num  2.62 2.88 2.32 3.21 3.44 ...
 $ qsec: num  16.5 17 18.6 19.4 17 ...
 $ vs  : num  0 0 1 1 0 1 0 1 1 1 ...
 $ am  : num  1 1 1 0 0 0 0 0 0 0 ...
 $ gear: num  4 4 4 3 3 3 3 4 4 4 ...
 $ carb: num  4 4 1 1 2 1 4 2 2 4 ...
```

Convert numberic variables into factors
========================================================
Here variables are converted into appropriate variable types and attach formats for factor variables.


```r
mtcars$cyl <- factor(mtcars$cyl,
                    levels=c(4,6,8),
                    labels=c("4 cyl","6 cyl","8 cyl"))

mtcars$gear <- factor(mtcars$gear,
                    levels=c(3,4,5), 
                    labels=c("3 gear","4 gear","5 gear"))

mtcars$am <- factor(mtcars$am,
                     levels=c(0,1), 
                     labels=c("automatic","manual"))

mtcars$carb <- factor(mtcars$carb,
                   levels=c(1,2,3,4,6,8), 
                   labels=c("1 carburetor","2 carburetors","3 carburetors",
                            "4 carburetors","6 carburetors","8 carburetors"))
```

Produce summary statistics
========================================================
Summary statistics provide detail summary of each variables.


```r
    summary(mtcars)
```

```
      mpg           cyl          disp             hp       
 Min.   :10.40   4 cyl:11   Min.   : 71.1   Min.   : 52.0  
 1st Qu.:15.43   6 cyl: 7   1st Qu.:120.8   1st Qu.: 96.5  
 Median :19.20   8 cyl:14   Median :196.3   Median :123.0  
 Mean   :20.09              Mean   :230.7   Mean   :146.7  
 3rd Qu.:22.80              3rd Qu.:326.0   3rd Qu.:180.0  
 Max.   :33.90              Max.   :472.0   Max.   :335.0  
      drat             wt             qsec             vs        
 Min.   :2.760   Min.   :1.513   Min.   :14.50   Min.   :0.0000  
 1st Qu.:3.080   1st Qu.:2.581   1st Qu.:16.89   1st Qu.:0.0000  
 Median :3.695   Median :3.325   Median :17.71   Median :0.0000  
 Mean   :3.597   Mean   :3.217   Mean   :17.85   Mean   :0.4375  
 3rd Qu.:3.920   3rd Qu.:3.610   3rd Qu.:18.90   3rd Qu.:1.0000  
 Max.   :4.930   Max.   :5.424   Max.   :22.90   Max.   :1.0000  
         am         gear               carb   
 automatic:19   3 gear:15   1 carburetor : 7  
 manual   :13   4 gear:12   2 carburetors:10  
                5 gear: 5   3 carburetors: 3  
                            4 carburetors:10  
                            6 carburetors: 1  
                            8 carburetors: 1  
```

Explor the data using plots
========================================================

![plot of chunk unnamed-chunk-4](presentation-figure/unnamed-chunk-4-1.png) 
