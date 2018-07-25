# Exercise 5.9

Assume the following two definitions:

`unsigned long ul1 = 3, ul2 = 7;`

What is the result of each of the following expressions?

(a) `ul1 & ul2`
(b) `ul1 && ul2`
(c) `ul1 | ul2`
(d) `ul1 || ul2`

**Answer**:

| var          | 0 | 1 | 2 | 3 | 4 | 5 ~ 31 | result |
| :----------: |:-:|:-:|:-:|:-:|:-:| :----: | :----: |
| ul1          | 1 | 1 | 0 | 0 | 0 | 0      | 3      |
| ul2          | 1 | 1 | 1 | 0 | 0 | 0      | 7      |
| ul1 & ul2    | 1 | 1 | 0 | 0 | 0 | 0      | 3      |
| ul1 && ul2   | - | - | - | - | - | -      | true   |
| ul1 \| ul2   | 1 | 1 | 1 | 0 | 0 | 0      | 7      |
| ul1 \|\| ul2 | - | - | - | - | - | -      | true   |