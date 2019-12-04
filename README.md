#### This covers the major topics in Data Analysis with R from scratch to Machine Learning and AI

* Environment: R, Jupyter Notebook, Docker, Mac OS Catalina 10.15.x
     * Initially working with Anaconda, I moved to Docker mainly because Docker can show Korean characters in R charts.
[Install Guideline for Docker](https://datascienceschool.net/view-notebook/03c5b5a96a614ee588a74f05c720e67c/)




### 0. Introduction to R for data analysis
1. Introduction
     * `help()`
     * `example()`
     * `version`
     * Pre-loaded dataset
2. Operators
     * `+` `-` `*` `/`
     * `%/%` Floor division // c.f. `//` in Python
     * `%%`  Modulus // Useful to check if values are True (1) or False (0) in Data Analysis
     * `**` `^`
3. Math Functions
     * `sqrt()` `abs()`
     * `trunc()` `round()`
     * `sum()` `mean()` `max()` `min()` `median()` // e.g. sum(iris$Sepal.Length)
4. Variables
    * scalar
    * vector `a <- c(10,20,30)` `a[1] = 10` // starting from 1 in R
5. Data Types
6. Operators with Variables
7. Boolean
     * `==` `!=` `>` `<` `>=` `<=`
     * `&` `|`
     * `xor(x,y)` True only if one of x,y is False
8. Testing Data Type: True (1) or False (0)
     * `is.numeric()` 
     * `is.integer()` 
     * `is.logical()`
     * `is.double()` float
     * `is.character()`
     * `is.data.frame()`
     * `is.factor()`
     * `is.Date()`
     * `is.na()` If 'sum(is.na(<data>) > 0', there is(are) NA
     * `is.nan()`
9. Converting Data Type
     * `as.numeric()` 
     * `as.integer()` 
     * `as.logical()`
     * `as.double()` float
     * `as.character()`
     * `as.data.frame()`
     * `as.factor()` // **useful** in data analysis
          * From `gender <- c('man', 'woman')` => character
          * To `f_gender <- as.factor(gender)` => Factor w/ 2 levels "man","woman": 1 2 
     * `as.Date()`
          * `as.Date('19/10/30', %y/%m/%d)`
          * `as.Date('2019/10/30', %Y/%m/%d)` 
          * `as.Date('19-10-30', %y-%m-%d)`
          * `as.Date('19/10/30', %y/%m/%d)` - 1' => 19/10/29
12. Basic Functions
     * `ls()` `rm()` Managing memory 
     * `Print()`, `Print( , quote=F)`
          * `sprintf("%s is %i years old, "John", 35)`
          * `sprintf(The weight of "%s is %5.2f, "boy", 12.25)`
          * `sprintf(The height of "%s is %5.1f, "boy", 103.5)`
13. Exploring Data
     * `head()` `tail()`
     * `unique()`
     * `class()`
     * `summary()`: check the distance between median and mean for each column
     * `str()`
     * `plot()`
     * `table()` `hist()`
