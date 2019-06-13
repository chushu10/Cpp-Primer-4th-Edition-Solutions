# Exercise 16.7

Explain each of the following function template definitions and identify whether any are illegal. Correct each error that you find.
(a) `template <class T, U, typename V> void f1(T, U, V);`
(b) `template <class T> T f2(int &T);`
(c) `inline template <class T> T foo(T, unsigned int*);`
(d) `template <class T> f4 (T, T);`
(e) `typedef char Ctype;`
    `template <typename Ctype> Ctype f5(Ctype a);`

**Answer**:

## (a)

```bash
ex1607.cc:1:21: error: expected template parameter
template <class T, U, typename V> void f1(T, U, V);
                    ^
// Correction
template <class T, class U, typename V> void f1(T, U, V);
```

## (b)

```bash
ex1607.cc:2:30: error: declaration of 'T' shadows template parameter
template <class T> T f2(int &T);
                             ^
// Correction
template <class T> T f2(T &t);
```

## (c)

```bash
ex1607.cc:3:1: error: ignoring 'inline' keyword on explicit template instantiation [-Werror,-Wstatic-inline-explicit-instantiation]
inline template <class T> T foo(T, unsigned int*);
^
// Correction
template <class T> inline T foo(T, unsigned int*);
```

## (d)

```bash
ex1607.cc:4:20: error: C++ requires a type specifier for all declarations
template <class T> f4 (T, T);
                   ^
// Correction
template <class T> T f4 (T, T);
```

## (e)

It is ok, however the `typedef char Ctype` became useless in the scope of `f5`.
