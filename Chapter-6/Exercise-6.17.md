# Exercise 6.17

Explain each of the following loops. Correct any problems you detect.

(a)

```cpp
do
    int v1, v2;
    cout << "Please enter two numbers to sum:";
    cin >> v1 >> v2;
    if (cin)
        cout << "Sum is: "
             << v1 + v2 << endl;
while (cin);
```

(b)

```cpp
do {
    // ...
} while (int ival = get_response());
```

(c)

```cpp
do {
    int ival = get_response();
    if (ival == some_value())
        break;
} while (ival);
if (!ival)
    // ...
```

**Answer**:

(a) Lack of open bracket after `do` and close bracket before `while`.

```cpp
// Correct version
do {
    int v1, v2;
    cout << "Please enter two numbers to sum:";
    cin >> v1 >> v2;
    if (cin)
        cout << "Sum is: "
             << v1 + v2 << endl;
} while (cin);
```

(b) The `do while` loop does not allow variable definitions (See Page 211 Section 6.9).

```cpp
int ival;
do {
    // ...
} while (ival = get_response());
```

(c) `ival` defined in `do` scope cannot be seen in the `while` or outside of the `do while` loop.

```cpp
int ival;
do {
    ival = get_response();
    if (ival == some_value())
        break;
} while (ival);
if (!ival)
    // ...
```