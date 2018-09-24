# Exercise 9.5

Why can we not have containers that hold `iostream` objects?

**Answer**:

The IO library types do not support copy or assignment. Therefore, we cannot have a container that holds objects of the IO types.