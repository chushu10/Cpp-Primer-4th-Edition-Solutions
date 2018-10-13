# Exercise 9.33

Which is the most appropriate `vector`, a `deque`, or a `list` for the following program tasks? Explain the rationale for your choice. If there is no reason to prefer one or another container explain why not?

a. Read an unknown number of words from a file for the purpose of generating English language sentences.
b. Read a fixed number of words, inserting them in the container alphabetically as they are entered. We'll see in the next chapter that associative containers are better suited to this problem.
c. Read an unknown number of words. Always insert new words at the back. Remove the next value from the front.
d. Read an unknown number of integers from a file. Sort the numbers and then print them to standard output.

**Answer**:

a. `vector` or `list` or `deque` are all OK choice. `vector` might be preferred for efficiency.
b. `list` of course for inserting elements in the middle of the container.
c. `deque` of course for inserting elements at the back and deleting elements from the front.
d. `list` of course for sorting elements need inserting or deleting elements in the middle of the container.