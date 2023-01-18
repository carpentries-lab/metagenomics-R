---
title: "R Data Types"
teaching: 10
exercises: 5
questions:
- "What types of data does the R language have?"
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

No matter how complicated our analysis can be, all data in R will belong to one of these
five data types. Data types are important because we want to know "who is who, and 
what is what". But this concept will help us learn one of the most powerful tools in R, which is 
the manipulation of diverse types of data together in what is called a **data-frame**.

## Data structures

Besides the data types, there are different ways of organizing the data in R called *data structures*. The simple data structure is the *vector*, which is a sequence of data of the same type. We can create a vector with the function `c()`.
~~~
> char_vector <- c("a", "a", "b", "b", "c", "c")
> typeof(char_vector)
~~~
{: .language-r}
~~~
[1] "character"
~~~
{: .output}

A more complex data structure is the *factor*, which holds the names of categories (called levels) and a sequence of the occurrences of those categories.
Here we can see how *factor* works:
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

And here, we can ask for the structure of the object.
~~~
> str(char_factor)
~~~
{: .language-r}
~~~
Factor w/ 3 levels "a","b","c": 1 1 2 2 3 3
~~~
{: .output}

Here, you see the levels of the factors and a sequence of numbers. Each number represents a level, and this sequence holds the information about which goes in which position. That is why we will get an "integer" if we ask about the type of data in the object.
~~~
> typeof(char_factor)
~~~
{: .language-r}
~~~
[1] "integer"
~~~
{: .output}

When we are dealing with categorical data, factors are the way to go.

> ## Exercise 1: Types and structures of data
> 
> Which type of data is present in each of the next vectors?:
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
> がんばって! (ganbatte; *good luck*):
>> ## Solution
>> The correct answer is: 
>> D) character, integer, complex.  
>>   
>> If we use `""` to define an object, R will read it as a character regardless we are typing numbers.  
>> The capital `L` after a number, indicates R to save that number as an
>> [Integer](https://stackoverflow.com/questions/23660094/whats-the-difference-between-integer-class-and-numeric-class-in-r).   
>> And each set of numbers with the letter 
>> `i` of imaginary, indicates R that this is a set of 
>> complex numbers.
> {: .solution}
{: .challenge} 

