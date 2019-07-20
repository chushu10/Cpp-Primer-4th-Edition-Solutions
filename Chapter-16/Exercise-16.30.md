# Exercise 16.30

Exercise 16.30:
Identify which, if any, of the following class template declarations (or declaration pairs) are illegal.

```cpp
(a) template <class Type> class C1;
    template <class Type, int size> class C1;
(b) template <class T, U, class V> class C2;
(c) template <class C1, typename C2> class C3 { };
(d) template <typename myT, class myT> class C4 { };
(e) template <class Type, int *ptr> class C5;
    template <class T, int *pi> class C5;
```

**Answer**:

(a) is illegal, you can't declare two template classes with the same class name even they have different template parameters.

(b) is illegal, it should be:

```cpp
template <class T, class U, class V> class C2;
```

(d) is illegal, it should be:

```cpp
template <typename myT> class C4 { };
// or
template <typename myT, class myT2> class C4 { };
```

(e) is ok, surprisingly! Because both declaration are the same, so that the second one overrides the first one.
