# Exercise 16.41

The `friend` declaration for `operator<<` in class `Queue` was

```cpp
friend std::ostream&
operator<< <Type> (std::ostream&, const Queue<Type>&);
```

What would be the effect of writing the `Queue` parameter as `const Queue&` rather than `const Queue<Type>&`?

**Answer**:

```bash
ex1632.cc:9:66: error: use of class template 'Queue' requires template arguments; argument deduction not allowed in function prototype
    friend std::ostream& operator<< <Type> (std::ostream&, const Queue&);
                                                                 ^~~~~
ex1632.cc:4:29: note: template is declared here
template <class Type> class Queue;
                            ^
1 error generated.
make: *** [ex1632] Error 1
```
