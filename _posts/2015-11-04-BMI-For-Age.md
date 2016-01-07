---   
layout: post
comments: true  
title: BMI For Age
---    

I build the R package <a href="https://github.com/epinotes/bmiage" target="_blank"> **bmiage** </a>  to ease the classification of BMI for age and sex. It uses CDC child bmi charts to assign each bmi to the four categories: *underweight*, *healthy weight*, *overweight* and *obese*.     

**To install the package:**, run these two lines of R codes.   


```r
devtools::install_github("epinotes/bmiage")
library(bmiage)
```


**Examples**  

Looking into the help files for the function *bmicat*


```r
?bmicat
```
When no dataset is provided try:
 

```r
bmicat(data = NULL,sex = "F",age = 18,wt.kg = 70 ,ht.m = 1.75, age.unit="year",bind = F)  
```

```
##        bmi bmicat
## 1 22.85714      1
```
 
Now let's create a dataframe df:


```r
 df <- data.frame(sex = c("F","M", "F"), age = c(18,15,NA), weight = c(70,50, 55), height = c(1.75, 1.60, 1.65))
```
We can use the new dataframe, df, with the function *bmicat*:


```r
 df <- bmicat(data = df,sex = sex,age = age,wt.kg = weight ,ht.m = height, age.unit="year",bind = T)
 
 df
```

```
##   sex age weight height      bmi bmicat
## 1   F  18     70   1.75 22.85714      1
## 2   M  15     50   1.60 19.53125      1
## 3   F  NA     55   1.65 20.20202     NA
```
 Now *df* has two added variables.  
   
