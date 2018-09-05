# Exercise 7.34

Define a set of overloaded functions named `error` that would match the following calls:

```cpp
int index, upperBound;
char selectVal;
// ...
error("Subscript out of bounds: ", index, upperBound);
error("Division by zero");
error("Invalid selection", selectVal);
```

**Answer**:

```cpp
void error(const string & , int , int );
void error(const string & );
void error(const string & , char );
```