# Exercise 14.24

Should the dereference or subscript operators defined in the previous exercise also check whether an attempt is being made to dereference or index one before the beginning of the array? If not, why not? If so, why?

**Answer**:

They should. Because that's the benefit of using class. If we use plain pointer, the program will probably crash if we dereference of index one before the beginning of the array. If our class prohibits us from doing such things, our program will be less error-prone.