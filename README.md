### This covers the major topics in Data Analysis with R from scratch to Machine Learning and AI

* Environment: R, Jupyter Notebook, Docker, Mac OS Catalina 10.15.x
     * Initially working with Anaconda, I moved to Docker mainly because Docker can show Korean characters in R charts.
[Install Guideline for Docker](https://datascienceschool.net/view-notebook/03c5b5a96a614ee588a74f05c720e67c/)


## 1. Introduction to R for data analysis
x. Vector
* assign & load
- `a <- c(10, 20, 30)` `a[1] => 10` `a[-1] => 20 30`// starting from 1 in R
- `a[1] <- 30` => `a
- `x <- rnorm(100)`
- `z <- 1:100` `z[1] =>  1` `z[c(2,50)] => 2 50``z[c(30:33),60)] = 30 31 32 33 60`
* `length()`
* `range()` // cf. `range()[1] == min()` `range()[2] == max()`
* `mean()` `var()` `sd()`
* vector merging
 - `append(3, 4)` => 3 4 `c(x, y)` => `3 4` // cf. `paste(x, y)` `'x, y'`
* operators
* squence
 - `seq(from = , to = , by = )` `seq( , , )`
* replicable `rep(  , times= )` `rep( , )`
 - `rep(1,5)` => `1 1 1 1 1`
 - `rep(c(2, 4), 3)` => `2 4 2 4 2 4` // cf. `rep(2, 4, 3)` => `2 2 2`
 - `rep(c('blue', 'green'), 3)` => `'blue' 'green' 'blue' 'green' 'blue' 'green'`
* `unique()`
* boolean

## 0. Introduction to R for data analysis
1. Introduction
     * `help()`
     * `example()`
     * `version`
     * `ls()` `rm()` Managing memory 
     * Pre-loaded dataset
2. Operators (with numbers and/or variables)
     * `+` `-` `*` `/`
     * `%/%` Floor division // cf. `//` in Python
     * `%%`  Modulus // Useful to check if values are True (1) or False (0) in Data Analysis
     * `**` `^`
4. Math Functions
     * `sqrt()` `abs()`
     * `trunc()` `round()`
     * `sum()` `mean()` `max()` `min()` `median()` // e.g. sum(iris$Sepal.Length)
5. Variables
    * scalar
    * vector 
6. Boolean
     * `==` `!=` `>` `<` `>=` `<=`
     * `&` `|`
     * `xor(x,y)` True only if one of x,y is False
7. Data Types
Testing Data Type: True (1) or False (0)
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
Converting Data Type
     * `as.numeric()` 
     * `as.integer()` 
     * `as.logical()`
     * `as.double()` float
     * `as.character()`
     * `as.data.frame()`
     * `as.factor()` // **useful** in data analysis
          * From `gender <- c('man', 'woman')` => character
          * To `factorGender <- as.factor(gender)` => 'Factor w/ 2 levels "man","woman": 1 2' 
     * `as.Date()`
          * `as.Date('19/10/30', %y/%m/%d)`
          * `as.Date('2019/10/30', %Y/%m/%d)` 
          * `as.Date('19-10-30', %y-%m-%d)`
          * `as.Date('19/10/30', %y/%m/%d) - 1` => 19/10/29
8. Print(), paste(), cat(paste())
     * `Print()` `Print( , quote=F)`
          * `sprintf("%s is %i years old, "John", 35)`
          * `sprintf(The weight of "%s is %5.2f, "boy", 12.25)`
          * `sprintf(The height of "%s is %5.1f, "boy", 103.5)`
     * print(paste("Hello", "World)" //  cf. `print("Hello", "World")` => `doesn't work' 
     * `cat(paste("Hello", "\n", "World")` `cat(paste("Hello\n", "World")`
     * `cat(paste("Hello", "\t", "World")` `cat(paste("Hello\t", "World")`
     * paste("Answer is: ", 10) => `'Answer is 10'`
9. Exploring Data
     * `head()` `tail()`
     * `unique()`
     * `class()`
     * `summary()`: check the distance between median and mean for each column
     * `str()`
     * `plot()`
     * `table()` `hist()`
