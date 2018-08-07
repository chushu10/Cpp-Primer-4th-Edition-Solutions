# Exercise 6.5

Correct each of the following:

(a)

```cpp
if (ival1 != ival2)
     ival1 = ival2
else ival1 = ival2 = 0;
```

(b)

```cpp
if (ival < minval)
    minval = ival; // remember new minimum
    occurs = 1;    // reset occurrence counter
```

(c)

```cpp
if (int ival = get_value())
    cout << "ival = " << ival << endl;
if (!ival)
    cout << "ival = 0\n";
```

(d)

```cpp
if (ival = 0)
    ival = get_value();
```

**Answer**:

(a)

```cpp
if (ival1 != ival2) {
    ival1 = ival2;
} else {
    ival1 = ival2 = 0;
}
```

(b)

```cpp
if (ival < minval) {
    minval = ival; // remember new minimum
    occurs = 1;    // reset occurrence counter
}
```

(c)

```cpp
if (int ival = get_value()) {
    cout << "ival = " << ival << endl;
} else if (!ival) {
    cout << "ival = 0\n";
}
```

(d)

```cpp
if (ival == 0) {
    ival = get_value();
}
```