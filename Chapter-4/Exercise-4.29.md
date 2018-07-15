# Exercise 4.29

Given the two program fragments int the highlighted box on page 138,

(a) Explain what the programs do.
(b) As it happens, on average, the `string` class implementation executes considerably faster than the C-style string functions. The relative average execution times on our more than five-year-old PC are as follows:

|        | Time in secs | Comment |
|:------:|:------------:|:--------|
| user   | 0.47 | # string class |
| user   | 2.55 | # C-style character string |

Did you expect that? How would you account for it?

**Answer**:

The programs are just loop 1000000 times, only copying the string to a variable and free it.

I did not expect that, since in my MacBook Pro (Retina, 13-inch, Mid 2014), the time used by C-style character string program is slightly less than `string` class program:

|        | Time in secs | Comment |
|:------:|:------------:|:--------|
| user   | 0.14 | # string class |
| user   | 0.11 | # C-style character string |

But I do recommend using `string` class instead of C-style string. It's simple and less error-prone, and just a little bit slower on my computer.