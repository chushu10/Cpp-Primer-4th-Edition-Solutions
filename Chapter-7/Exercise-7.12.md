# Exercise 7.12

When would you use a parameter that is a pointer? When would you use a parameter that is a reference? Explain the advantages and disadvantaged of each.

**Answer**:

|  | Advantages | Disadvantages |
|:-|:-----------|:--------------|
| Pointer   | As far as I learned, nearly every situation, you can use references to replace pointers. Pointer has no advantages over reference in C++ | <li>May be dangerous</li><li>May be misleading</li><li>May be hard to use</li> |
| Reference | <li>Avoid copying arguments</li><li>Return additional information</li><li>Safer and more natural</li><li>Ensures that the size of the array match</li> | One has to get used to reference when switching from C to C++ |