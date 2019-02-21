# Exercise 15.16

Given the following base class definition,

```cpp
struct Base {
    Base(int val): id(val) { }
protected:
    int id;
};
```

explain why each of the following constructors is illegal.

(a)

```cpp
struct C1 : public Base {
    C1(int val): id(val) { }
};
```

(b)

```cpp
struct C2 : public C1 {
    C2(int val): Base(val), C1(val) { }
};
```

(c)

```cpp
struct C3 : public C1 {
    C3(int val): Base(val) { }
};
```

(d)

```cpp
struct C4 : public Base {
    C4(int val) : Base(id + val){ }
};
```

(e)

```cpp
struct C5 : public Base {
    C5() { }
};
```

**Answer**:

(a) is illegal, because we should **respect** the initialization intent of its base class `Base`, the right way is to explicitly call the constructor of `Bsse`:

```cpp
struct C1 : public Base {
    C1(int val): Base(val) { }
};
```

(b) is illegal, `C2` cannot invoke constructor of its indirect base class `Base`, just let `C1` do the work:

```cpp
struct C2 : public C1 {
    C2(int val): C1(val) { }
};
```

(c) is illegal, same reason as (b).

(d) is legal, but we have a warning here:

```bash
warning: base class 'Base' is uninitialized when used here to access 'Base::id' [-Wuninitialized]
    C4(int val) : Base(id + val){ }
                       ^
1 warning generated.
```

(e) is illegal, because there is no default constructor of `Base`, the right way is to create a default constructor:

```cpp
struct Base {
    Base(int val = 0): id(val) { }
protected:
    int id;
};
```