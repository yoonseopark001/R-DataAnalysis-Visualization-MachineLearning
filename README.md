### This covers the major topics in Data Analysis with R from scratch to Machine Learning and AI

* Environment: R, Jupyter Notebook, Docker, Mac OS Catalina 10.15.x
* Initially working with Anaconda, I moved to Docker mainly because Docker can show Korean characters in R charts.
* [Install Guideline for Docker](https://datascienceschool.net/view-notebook/03c5b5a96a614ee588a74f05c720e67c/)


## 1. Introduction to R for data analysis
### 1. Operators (with numbers and/or variables)
* `+` `-` `*` `/`
* `%/%` Floor division // cf. `//` in Python
* `%%`  Modulus // Useful to check if values are True (1) or False (0) in Data Analysis 
* `**` `^`
* Set operators: `union(x,y)` `intersect(x,y)` `setdiff(x,y)` // `sediff(totalPop, asiaPop)` total population - Asia population
### 2. Math Functions
* `sqrt()` `abs()`
* `trunc()` `round()`
* `sum()`
  - e.g. `sum(iris$Sepal.Length)` // sum of column Sepal.Length in iris dataset
  - e.g. `sum(10, 20, 20, NA, na.rm = T)` // remove(ignore) NA value
  - e.g. `sum(data[1,])` // sum of 1st row
  - e.g. `sum(data[,3])` // sum of 3rd column
* `mean()` `max()` `min()` `median()`
* `na.rm = T` // e.g. `sum(c(10, 20, NA, 40), na.rm = T)`
### 3. Boolean
* `==` `!=` `>` `<` `>=` `<=`
* `&` `|`
* `xor(x,y)` True only if one of x,y is False
* `any(x >= 1)` `all(x < 1)` // data size test
* `is.vector(x)` // data type Test
### 4. Testing Data Type: True (1) or False (0)
* `is.numeric()` 
* `is.integer()` 
* `is.logical()`
* `is.double()` float
* `is.character()`
  - `example <- c(1, 2, '3')` => `'1' '2' '3'` // entire elements of `example` turns to character
* `is.data.frame()`
* `is.factor()`
* `is.Date()`
* `is.na()` If 'sum(is.na(<data>) > 0', there is(are) NA
* `is.nan()`
### 5. Converting Data Type
* `as.numeric()` 
* `as.integer()` 
* `as.logical()`
* `as.double()` float
* `as.character()`
* `as.data.frame()`
* `as.factor()` // useful in data analysis
  * From `gender <- c('man', 'woman')` => character
  * To `factorGender <- as.factor(gender)` => 'Factor w/ 2 levels "man","woman": 1 2' 
* `as.Date()`
  * `as.Date('19/10/30', %y/%m/%d)`
  * `as.Date('2019/10/30', %Y/%m/%d)` 
  * `as.Date('19-10-30', %y-%m-%d)`
  * `as.Date('19/10/30', %y/%m/%d) - 1` => 19/10/29   
### 6. Print
* `Print()` `Print( , quote=F)`
  * `sprintf("%s is %i years old, "John", 35)`
  * `sprintf(The weight of "%s is %5.2f, "boy", 12.25)`
  * `sprintf(The height of "%s is %5.1f, "boy", 103.5)`
* `print(paste("Hello", "World)"` //  cf. `print("Hello", "World")` => doesn't work
* `cat(paste("Hello", "\n", "World")` `cat(paste("Hello\n", "World")`
* `cat(paste("Hello", "\t", "World")` `cat(paste("Hello\t", "World")`
* `paste("Answer is: ", 10)` => `'Answer is 10'`
* `paste("2019", "11", "01")` => `'2019 11 01'`
* `paste("2019", "11", "01", sep=".")` => `'2019.11.01'` // sep=" ", sep="-"
* `paste(x, collapse = "-")` => `'1-2-3'` where x = c(1, 2, 3)  
### 7. Vector
* assign & load
- `a <- c(10, 20, 30)` `a[1]` => `10` `a[-1]` => `20 30`// starting from 1 in R
- `a[1] <- 30` => 'a': 30 20 30
- `x <- rnorm(100)`
- `z <- 1:100` `z[1] =>  1` `z[c(2,50)] => 2 50``z[c(30:33),60)] = 30 31 32 33 60`  
```
number <- 1:10
myVector <- c()   # assign blank(NULL)
for(i in number){
    print(i * 2)  # it is a just print output
    myVector[i] <- i * 2   # the results should be assigned into myVector if you want to use it.
}
```
* `length()` 
* `range()` // cf. `range()[1] == min()` `range()[2] == max()`
* operators
* `mean()` `var()` `sd()`
* vector merging
- `append(3, 4)` => `3 4` `c(x, y)` => `3 4` // cf. `paste(x, y)` `'x, y'`
* squence
- `seq(from = , to = , by = )` `seq( , , )`
* replicable `rep(  , times= )` `rep( , )`
- `rep(1,5)` => `1 1 1 1 1`
- `rep(c(2, 4), 3)` => `2 4 2 4 2 4` // cf. `rep(2, 4, 3)` => `2 2 2`
- `rep(c('blue', 'green'), 3)` => `'blue' 'green' 'blue' 'green' 'blue' 'green'`
* `unique()`
* boolean `x == y` => `TRUE FALSE TRUE` where `x <- c(1, 2, 3)` `y <- c(1, 8, 5)`
### 8. Data Frame  
* Creating data.frame
- `num = c(1:5)`
- `name = c("Snack", "Bread", "Juice", "Milk", "Candy")`
- `price = c(5, 3, 3, 2, 1)`
- `qty = c(100, 50, 80, 90, 150)`
- `supermarket <- data.frame(Number = num, Name = name, Price = price, Quantity = qty)`
* Handling
- `supermarket[1,]` // 1st row
- `supermarket[,1:3]` // 1st, 2nd, 3rd columns `supermarket[1:3]`
- `supermarket[1:3,c(2,4)]` // returns 'rows from 1 to 3' and '2nd & 4th columns'
- `supermarket[3]` // 3rd column 
- 'supermarket$price' // useful to simply access column data                  
cf. `supermarket[,3]` or 'supermarket$price' returns `vector` `5 3 3 2 1` as a `numeric` `class`
  - add `colnames` if needed after `cbind`
* converting to data frame `as.data.frame()`
* merging dataframes based on 'key' `cbind` and `merge()`
- If two (or more) data frames are in order, 'cbind(colA, colB)' is one way to do it.
  - e.g. `cbind(height[1:2], weight[1])` where height and weight are in order
- If those are not in order, `merge(x = df1, y = df2, by.x = "key of x", by.y = "key of y")`
  - e.g. `merge(height, weight, by.x = "ID(height's key)", by.y = "ID_Num(weight's key)")
- Of course, you can still use `cbind`, if you order keys(index) using `orderBy` beforehand.
 * `nrow()` `ncol()` 
### 9. etc ###
* `help()`
* `example()`
* `version`
* `ls()` `rm()` managing memory 
* `readline()`  The value is input as `character`. If needed calculation, use as.integer() or as.numeric
* Pre-loaded dataset

## 2. Data Handling in R
### 1. Load Data file
* `read.csv("path") // `read.csv("./Data/example.csv")`
### 2. Exploring Data
* `head()` `tail()`
* `unique()`
* `class()`
* `summary()` // to check the distance between median and mean for each column
* `str()`
* `plot()`
* `table()` `hist()`// to check frequency

### 3. Extracting or replacing substrings in a character vector // useful in data cleansing

#### A. `substring` function
  * `substring("    ", from, to)`
  * `substring("abcdefg", 3, 5)` => `cde`
  * `substring(strSamp, 4, 8)` => `'bbbbb' 'ccccc'` where `strSamp <- c("aaabbbbb", "aaaccccc")`
  * `substring(strDate, 1, 4)` => `'2018' '2019'`  where `strDate <- c("2018-11-01", "2019-11-01")`
  
#### B. `stringr` package
  * Package: `install.packages("stringr")` `library(stringr)`
  
  * `str_extract()` `str_extract_all()` 
  
     (1) extract finding values, which is a type of list(key + value) in characters
      * `strR <- "HEbLLc12fO34hijiWORip099LD8ys766pa"`
      * str_extract(data, "[from-to]{digits)") // [from-to]: e.g. [0-9] [A-Z] [A-z] [가-힣] [^A-z] ^ means NOT// {digit}: e.g. {1} {2,} 2 or above 
        - `str_extract(strR, "[0-9]")` => `'1'` // the first number from 0 to 9 of `strr` is `'1'`
        - `str_extract(strR, "[2-9]{2}")` => `'34'` // the first 2-digit number from 2 to 9 of`strr` is `'34'`
      * str_extract_all(data, "[from-to]{digits)")
        - `str_extract_all(strR, "[2-9]{2,}")` => `1. '34' '99' '766'`
        - `str_extract_all(strR,"[A-Z]{1,}") => `1. 'HE' 'LL' 'O' 'WOR' 'LD'`
        - `str_extract_all(strR,"[^A-z]") => `'1' '2' '3' '4' '0' '9' '9' '8' '7' '6' '6'`
        - `str_extract_all(strR,"LL") => `1. LL`
      * the `class` of the return is `list` with e.g. key: 1 and value: '34' '98' '76'

     (2) unlist (1) to convert it into vector: `unlist(str_extract_all(strR, "[2-9]{2}"))` => `'34' '99' '76'` 

     (3) convert (2) into numeric: `number as.numeric(unlist(ste_extract_all(strR, "[2-9]{2}")))` => `34 99 76`

  * `str_length()` 
  * `str_locate(data,"finding value")` returns `start` and `end`
  * `str_to_upper()` `str_to_lower()`
  * `str_replace()` `str_replace_all(data,"as-is","to-be")` // start test-run with `str_replace`, then `str_replace_all
       * `str_replace_all(data, "as-is", " "): to eliminate "as-is // useful tip! (e.g. web crawling, word cloud, NLP)
  * `str_c()` // add additional string to the existing ond
  * `str_sub(data, from, to)` // substring
  * `str_spilit(data, "separate value")` // e.g. `str_spilit(data, ".")`

### 4. Combining by rows or columns
  * `mat1 <- rbind(jan, feb, mar)` //  e.g. to add data from the latest information
  * `mat2 <- cbind(height, weight, age)` //  e.g. to add new category

### 5. Naming rows and columns
  * `rownames(mat1) <- c("Jan", "Feb", "Mar")`
  * `colnames(mat2) <- c("Height", "Weight", "Age")`     

## 2. Loop 
[*Exercise 01: Multiplication Tables*](https://github.com/yoonseopark001/Data-Analysis-with-R/blob/master/R_Exercise%2001%20Multiplication%20Tables.ipynb)

### 1. if
  * if: `if("condition") {<yes>}`
  * if else: `if("condition") {<yes>} else {<no>}`
       * if("condition") {<yes>} else if("condition"{<yes>} else if("condition"{<yes>} else{<no>} [*Exercise 02: Grade*](https://github.com/yoonseopark001/Data-Analysis-with-R/blob/master/R_Exercise%2002%20Grade.ipynb)
  * ifelse: `ifelse("condition", <yes>, <no>}` // vector allowed only in ifelse

```
if(numb %% 2 == 0){
           print("it's even")
           }else{
           print("it's odd")
}
```

```
score <- c(85, 95, 98)
name  <- c("Adam", "Brad", "Carl")

for(i in 1:3)
    cat(paste(name[i],"=>", score[i],"\n"))

Adam => 83
Brad => 92
Carl => 98
```

* alternatively,
```
i <- 1
for(s in score){
    cat(paste(name[i],"=>", s,"\n"))
```
    
### 2. for: when you know how many times the loop should run
```
sum1 <- 0
    for (i in 1:1000){
         sum1 <- sum1 + i
}
```

### 3. while: when you don't know how many times the loop should run
* while(condition): sum of numbers from 1 to 100
```
sum <- 0             # variable to be cummulative
i <- 1               # starting point

while(i <= 100){
    sum <- sum + i
    i <- i + 1       # incremental
} 
print(sum)
```
* while(T) and break condition
```
sum <- 0 
i <- 1

while(T){                 
    sum <- sum + i
    i <- i + 1
    if (sum > 100){
        break}            # break condition
}
print(i)
print(sum)
```
### 3. repeat // seldom used in data analysis
```
sum <- 0
i <- 1

repeat{
    sum <- sum + i 
    i <- i + 1
    if(i > 10){ 
        break
    }
}
```

print(sum)

## 2. Function
- [*Exercise 03: Frequency Table of Survey*](https://github.com/yoonseopark001/Data-Analysis-with-R/blob/master/R_Exercise_03%20Frequency%20Table%20of%20Survey.ipynb)


. Random Generator

* `runif()` `runif(num, min = , max = )` // default `min = 0` `max = 1`
* random integer generation: `trunc(runif(5,1,20)`
* `rnorm ()` `rnorm(num, mean = , sd = )` // default `mean = 0` `sd = 1`                                     

NA: Not Available / NaN: Not a Number


# Exercise
- [*Exercise 01: Multiplication Tables*](https://github.com/yoonseopark001/Data-Analysis-with-R/blob/master/R_Exercise%2001%20Multiplication%20Tables.ipynb)
- [*Exercise 02: Grade*](https://github.com/yoonseopark001/Data-Analysis-with-R/blob/master/R_Exercise%2002%20Grade.ipynb)
- [*Exercise 03: Frequency Table of Survey*](https://github.com/yoonseopark001/Data-Analysis-with-R/blob/master/R_Exercise_03%20Frequency%20Table%20of%20Survey.ipynb)

