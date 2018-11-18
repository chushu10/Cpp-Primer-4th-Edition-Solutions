# Exercise 12.18

Explain the following code. Indicate which definition of `Type` or `initVal` is used for each use of those names. If there are any errors, say how you would fix the program.

```cpp
typedef string Type;
Type initVal();
class Exercise {
public:
    // ...
    typedef double Type;
    Type setVal(Type);
    Type initVal();
private:
    int val;
};

Type Exercise::setVal(Type parm) {
    val = parm + initVal();
}
```

The definition of the member function `setVal` is in error. Apply the necessary changes so that the class `Exercise` uses the global typedef `Type` and the global function `initVal`.

**Answer**:

Code explanation using comments:

```cpp
typedef string Type;
Type initVal();
// This class has one private member val which is of type int
// It has two member functions, in which initVal seems to return a initial value of type Type
// and setVal set the value of val by plus its parameter parm with value returned by initVal
class Exercise {
public:
    // ...
    typedef double Type;
    Type setVal(Type); // Exercise::Type
    Type initVal(); // Exercise::Type
private:
    int val;
};

Type Exercise::setVal(Type parm) { // Type(first), Exercise::Type(second)
    val = parm + initVal(); // Exercise::Type, Exercise::initVal();
}
```

A name used in the body of a member function is resolved as follows:

1. Declarations in the member-function local scopes are considered first.
2. If the a declaration for the name is not found in the member function, the declarations for all the class members are considered.
3. If a declaration for the name is not found in the class, the declarations that appear in scope before the member function definition are considered.

Names used in the declarations of a class member are resolved as follows:

1. The declarations of the class members that appear before the use of the name are considered.
2. If the lookup in step 1 is not successful, the declarations that appear in the scope in which the class is defined, and that appear before the class definition itself, are considered.

Fix:

```cpp
// Type and initVal declared out of class Exercise are bad designed, so we commented them
// typedef string Type;
// Type initVal();
class Exercise {
public:
    // ...
    typedef int Type; // We don't want to add an int type to a double type
    void setVal(Type);
    Type initVal() {
        return 1; // any initial value
    }
private:
    int val;
};

void Exercise::setVal(Type parm) { // setVal should return void, because it only sets something
    val = parm + initVal();
}
```