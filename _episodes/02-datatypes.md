---
title: "R Data Types"
teaching: 10
exercises: 5
questions:
- "What types of data does the R language has?"
objectives:
- "Learn the types of data that we can manage in R."
keypoints:
- "R uses different types of data to store information."
---
## Types of data

We already used numbers to generate a result. But this is not the only type of data that RStudio 
can manage. We can use the command `typeof()` to corroborate the data type of our object `addition`:

~~~
> typeof(addition)
~~~
{: .language-r}

~~~
> [1] "double"
~~~
{: .output}

There are five types of data in RStudio:
* Double
* Integer
* Complex
* Logical
* Character

~~~
> typeof(5L) #Integer type can contain only whole numbers followed by a capital L
~~~
{: .language-r}
~~~
[1] "integer"
~~~
{: .output}

~~~
> typeof(72+5i)
~~~
{: .language-r}
~~~
[1] "complex"
~~~
{: .output}

~~~
> addition == subtraction
~~~
{: .language-r}
~~~
[1] FALSE
~~~
{: .output}

~~~
> typeof(addition == subtraction)
~~~
{: .language-r}
~~~
[1] "logical"
~~~
{: .output}

~~~
> result <- "4 and 3 are not the same on Earth. On Mars maybe... "
> typeof(result)
~~~
{: .language-r}
~~~
[1] "character"
~~~
{: .output}

No matter how complicated our analysis can become, all data in R will be allocated as one of this
five data types. On their own, data types are important because we want to know "who is who, and 
what is what". But this concept will help us learn one of the most powerful tools in R, which is 
the manipulation of different types of data at the same time in a data-frame.

## Data structures

Besides the data types, there are different ways of organizing the data in R called *data structures*. The basic data structure is the *vector*, which is a sequence of data of the same type. We can create a vector with the function `c()`.
~~~
> char_vector <- c("a", "a", "b", "b", "c", "c")
> typeof(char_vector)
~~~
{: .language-r}
~~~
[1] "character"
~~~
{: .output}

A more complex data structure is the factor, which holds names of categories (called levels) and a sequence of the occurrences of those categories.
Here we can see the factor itself:
~~~
> char_factor <- as.factor(char_vector)
> char_factor
~~~
{: .language-r}
~~~
[1] a a b b c c
Levels: a b c
~~~
{: .output}

And here, we can ask what the structure of the object is.
~~~
> str(char_factor)
~~~
{: .language-r}
~~~
Factor w/ 3 levels "a","b","c": 1 1 2 2 3 3
~~~
{: .output}

Here you see the levels of the factor and a sequence of numbers. Each number represents a level, and this sequence holds the information about which level goes in which position. This is why if we ask for the type of the factor we will get integer.
~~~
> typeof(char_factor)
~~~
{: .language-r}
~~~
[1] "integer"
~~~
{: .output}

When we are dealing with categorical data, factors are the way to go.

> ## Exercise 1: Types and structures fo data
> 
> Which type of data are in each of the next three vectors?:
> 
> `ej1 <- c("34","147","26+7i")`
>
> `ej2 <- c(4L,12L,152L)`
>
> `ej3 <- c(34,147,26+7i)`
> 
> A) numerical, integer, numerical
>
> B) character, numerical, numerical
>
> C) numerical, complex, character
>
> D) character, integer, complex
>
> がんばれ! (ganbate; *good luck*):
>> ## Solution
>> The correct answer is: 
>> D) character, integer, complex.  
>>   
>> If we use `""` to define an object, R will read it as a character regardless we are typing numbers.  
>> The capital `L` after a number, gives the indication to R to save that number as an
>> [Integer](https://stackoverflow.com/questions/23660094/whats-the-difference-between-integer-class-and-numeric-class-in-r).   
>> And each set of numbers with the letter 
>> `i` of imaginary, gives the indication to R that this is a set of 
>> complex numbers.
> {: .solution}
{: .challenge} 

