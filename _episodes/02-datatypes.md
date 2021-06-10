
### Types of data

We already used numbers to generate a result. But this is not the only type of data that RStudio 
can manage. We can use the command `typeof()` to corroborate the data type of our object `suma`:

~~~
> typeof(suma)
~~~
{: .language-r}

~~~
> [1] "double"
~~~
{: .output}

There are five types of data in RStudio:
* Double
* [Integer](https://stackoverflow.com/questions/23660094/whats-the-difference-between-integer-class-and-numeric-class-in-r#:~:text=R%20handles%20the%20differences%20between,for%20you%20in%20the%20background.&text=(Putting%20capital%20'L'%20after,a%20subset%20of%20%22numeric%22.&text=Integers%20only%20go%20to%20a,numerics%20can%20be%20much%20bigger.))
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
> suma == resta
~~~
{: .language-r}
~~~
[1] FALSE
~~~
{: .output}

~~~
> typeof(suma == resta)
~~~
{: .language-r}
~~~
[1] "logical"
~~~
{: .output}

~~~
> resultado <- "4 and 3 are not the same in Earth. In Mars maybe... "
> typeof(resultado)
~~~
{: .language-r}
~~~
[1] "character"
~~~
{: .output}

Also, we can use `c()` command to enlist a certain number of objects that we want to use. This can
be accomplished by enlisting them inside the parenthesis, and separe each element by a comma. Let's 
create a vector and found out its class:
~~~
> v.examp <- c("his ", "scabbard", "of", "chalcedony")
> typeof(v.examp)
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
