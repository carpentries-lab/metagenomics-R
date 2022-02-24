---
title: "Dataframes manipulation"
teaching: 10
exercises: 10
questions:
- "Data-frames. What they are and how to manage them? "
objectives:
- "Understand what is a data-frame and manipulate it."
keypoints:
- "Data-frames contain multiple columns with different types of data."
---
### Data-frames: The power of interdisciplinarity 
Let's beggin by creating a mock data set:
~~~
> musician <- data.frame(people = c("Medtner", "Radwimps", "Shakira"),
						 pieces = c(722,187,68),
 						 likes = c(0,1,1))
> musician
~~~
{: .language-r}
The content of our new object:
~~~
    people pieces likes
1  Medtner    722     0
2 Radwimps    187     1
3  Shakira     68     1
~~~
{: .output}

We have just created our first data-frame. We can see if this is true by the `class()` command:
~~~
> class(musician)
~~~
{: .language-r}
~~~
[1] "data.frame"
~~~
{: .language-r}
A data-frame is a collection of vectors, a list, whose components must be of the same data type within
each vector. Whereas, a data-frame can save vectors of different data types:

<a href="https://user-images.githubusercontent.com/67386612/118735756-b4595500-b806-11eb-8bd6-d189b9463eca.png">
  <img src="https://user-images.githubusercontent.com/67386612/118735756-b4595500-b806-11eb-8bd6-d189b9463eca.png" />
</a>
<em>Figure 3. Structure of the created data-frame.<em/>

We can begin to explore our new object by pulling out columns by the `$` operator. In order to use it, 
you need to write the name of your data-frame, followed by the `$` operator and the name of the column 
you want to extract:
~~~
> musician$people
~~~
{: .language-r}
~~~
[1] "Medtner"  "Radwimps" "Shakira" 
~~~
{: .output}

We can do operations with our columns 
~~~
> musician$pieces + 20
~~~
{: .language-r}
~~~
[1] 742 207  88
~~~
{: .output}

Moreover, we can change the data type of one of the columns. By the next code we can see if the musicians are 
popular or not:
~~~
> typeof(musician$likes)
~~~
{: .language-r}
~~~
[1] "double"
~~~
{: .output}

~~~
> musician$likes <- as.logical(musician$likes)
> paste("Is",musician$people, "popular? :", musician$likes, sep = " ")
~~~
{: .language-r}
~~~
[1] "Is Medtner popular? : FALSE" "Is Radwimps popular? : TRUE" "Is Shakira popular? : TRUE"
~~~
{: .output}

Finally, we can extract information from a specific place in our data by using the "matrix" nomenclature `[-,-]`,
where the first number inside the brackets specifies the number of row, and the second the number of the column:

<a href="https://user-images.githubusercontent.com/67386612/119908857-2a517080-bf19-11eb-8e0f-b3da6d1dcfc0.png">
  <img src="https://user-images.githubusercontent.com/67386612/119908857-2a517080-bf19-11eb-8e0f-b3da6d1dcfc0.png" />
</a>
<em>Figure 4. Extaction of specific data in a data-frame and a matrix.<em/>
~~~
> musician[1,2]  # The number of pieces that Nikolai Medtner composed
~~~
{: .language-r}
~~~
[1] 722
~~~
{: .output}




