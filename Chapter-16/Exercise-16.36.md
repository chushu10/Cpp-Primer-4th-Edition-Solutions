# Exercise 16.36

Explain what instantiations, if any, are caused by each labeled statement.

```cpp
template <class T> class Stack { };
void f1(Stack<char>);                   // (a)
class Exercise {
    Stack<double> &rsd;                 // (b)
    Stack<int> si;                      // (c)
};
int main() {
    Stack<char> *sc;                    // (d)
    f1(*sc);                            // (e)
    int iObj = sizeof(Stack< string >); // (f)
}
```

**Answer**:

(a) no instantiation.
(b) instantiation of class `Stack<double>`.
(c) instantiation of class `Stack<int>`.
(d) instantiation of class `Stack<char>`
(e) instantiation of class `Stack<char>`
(f) no instantiation.
