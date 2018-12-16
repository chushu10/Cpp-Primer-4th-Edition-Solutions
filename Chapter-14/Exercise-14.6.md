# Exercise 14.6

Explain why and whether each of the following operators should be class members:

```cpp
(a) + (b) += (c) ++ (d) -> (e) << (f) && (g) == (h) ()
```

**Answer**:

(a) `+` is best defined as nonmember since it is a symmetric operator(arithmetic).
(b) `+=` is best defined as member since it changes the state of the object.
(c) `++` is best defined as member since it changes the state of the object.
(d) `->` must be defined ad member.
(e) `<<` can be a member or a nonmember, it just has to return the reference to its right hand operand.
(f) `&&` is best defined as nonmember since it is a symmetric operator(relational).
(g) `==` is best defined as nonmember since it is a symmetric operator(relational).
(h) `()` must be defined ad member.