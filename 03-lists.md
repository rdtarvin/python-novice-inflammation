---
layout: page
title: Programming with Python
subtitle: Storing Multiple Values in Lists
minutes: 30
---
> ## Learning Objectives {.objectives}
>
> *   Explain what a list is.
> *   Create and index lists of simple values.

Just as a `for` loop is a way to do operations many times,
a list is a way to store many values.
Unlike NumPy arrays,
lists are built into the language.
We create a list by putting values inside square brackets:

~~~ {.python}
odds = [1, 3, 5, 7]
print 'odds are:', odds
~~~

We select individual elements from lists by indexing them:

~~~ {.python}
print 'first and last:', odds[0], odds[-1]
~~~

and if we loop over a list,
the loop variable is assigned elements one at a time:

~~~ {.python}
for number in odds:
    print number
~~~

There is one important difference between lists and strings:
we can change the values in a list,
but we cannot change the characters in a string.
For example:

~~~ {.python}
names = ['Newton', 'Darwing', 'Turing'] # typo in Darwin's name
print 'names is originally:', names
names[1] = 'Darwin' # correct the name
print 'final value of names:', names
~~~

works, but:

~~~ {.python}
name = 'Bell'
name[0] = 'b'
~~~

does not.

> ## Ch-Ch-Ch-Changes {.callout}
>
> Data that can be changed is called [mutable](reference.html#mutable),
> while data that cannot be is called [immutable](reference.html#immutable).
> Like strings,
> numbers are immutable:
> there's no way to make the number 0 have the value 1 or vice versa
> (at least, not in Python --- there actually *are* languages that will let people do this,
> with predictably confusing results).
> Lists and arrays,
> on the other hand,
> are mutable:
> both can be modified after they have been created.
>
> Programs that modify data in place can be harder to understand than ones that don't
> because readers may have to mentally sum up many lines of code
> in order to figure out what the value of something actually is.
> On the other hand,
> programs that modify data in place instead of creating copies that are almost identical to the original
> every time they want to make a small change
> are much more efficient.

There are many ways to change the contents of in lists besides assigning to elements:

~~~ {.python}
odds.append(11)
print 'odds after adding a value:', odds
~~~
~~~ {.output}
[1, 3, 5, 7, 11]
~~~

~~~ {.python}
del odds[0]
print 'odds after removing the first element:', odds
~~~
~~~ {.output}
[3, 5, 7, 11]
~~~

~~~ {.python}
odds.reverse()
print 'odds after reversing:', odds
~~~
~~~ {.output}
[11, 7, 5, 3]
~~~
