# Exercise 15.25

Assume `Derived` inherits from `Base` and that `Base` defines each of the following functions as virtual. Assuming `Derived` intends to define its own version of the virtual, determine which declarations in `Derived` are in error and specify what's wrong.

(a)

```cpp
Base* Base::copy(Base*);
Base* Derived::copy(Derived*);
```

(b)

```cpp
Base* Base::copy(Base*);
Derived* Derived::copy(Base*);
```

(c)

```cpp
ostream& Base::print(int, ostream&=cout);
ostream& Derived::print(int, ostream&);
```

(d)

```cpp
void Base::eval() const;
void Derived::eval();
```

**Answer**:

(a) Error. `Derived::copy` hides the definition of `Base::copy`, because they takes different parameter.
(b) Correct.
(c) Error. `Derived::print` hides the definition of `Base::print`, because the default argument is not inherited to `Derived`. See this [StackOverflow Q&A](https://stackoverflow.com/questions/3533589/can-virtual-functions-have-default-parameters) for details.
(d) Error. `Derived::eval` hides the definition of `Base::eval`, because the return type of `Base::eval` is `const` which is different from `Derived::eval()`.