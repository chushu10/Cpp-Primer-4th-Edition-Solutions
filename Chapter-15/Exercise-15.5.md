# Exercise 15.5

Which of the following declarations, if any, are incorrect?

```cpp
class Base { ... };

(a) class Derived : public Derived { ... };
(b) class Derived : Base { ... };
(c) class Derived : private Base { ... };
(d) class Derived : public Base;
(e) class Derived inherits Base { ... };
```

**Answer**:

(a) Incorrect, you cannot derive a class from itself.
(b) Incorrect, the derivation list is not complete. We should specify access label to the derived class. For example:

```cpp
class Derived : protected Bsse { ... };
```

(c) Correct.
(d) Incorrect, we can't declare a derived class that includes its derivation list. The correct form is:

```cpp
class Derived;
```

(e) Incorrect, there is no `inherits` keyword in C++.