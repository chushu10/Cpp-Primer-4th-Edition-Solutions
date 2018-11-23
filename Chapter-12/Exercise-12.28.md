# Exercise 12.28

Explain whether the `Sales_item` constructor that takes a `string` should be `explicit`. What would be the benefits of making the constructor `explicit`? What would be the drawbacks?

**Answer**:

Should be, because if we pass a `string` to `same_isbn` function, we may implicitly convert the `string` to a `Sales_item` object.
Benefits: Making constructors `explicit` may avoid mistakes, and a user can explicitly construct an object when a conversion is useful.
Drawbacks: It's a little bit weird to have `explicit` keyword before constructors, and sometimes we might want to define an implicit conversion.