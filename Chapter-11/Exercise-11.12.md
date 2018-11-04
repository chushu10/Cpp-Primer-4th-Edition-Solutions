# Exercise 11.12

Why was it be necessary to use `erase` rather than define a generic algorithm that could remove elements from the
container?

**Answer**:

Because a generic algorithm should not care about the type of the containers it operates on. Since the implementations of `vector`s and `list`s and may other containers have different strategies of organizing elements, It it best to let themselves to implement the `erase` function.