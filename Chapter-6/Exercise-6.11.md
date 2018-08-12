# Exercise 6.11

Explain each of the following loops. Correct any problems you detect.

(a)

```cpp
string buffString, word;
while (cin >> bufString >> word) { /* ... */ }
```

(b)

```cpp
while (vector<int>::iterator iter != ivec.end())
{ /* ... */ }
```

(c)

```cpp
while (ptr = 0)
    ptr = find_a_value();
```

(d)

```cpp
while (bool status = find(word))
{ word = get_next_word(); }
if (!status)
    cout << "Did not find any words\n";
```

**Answer**:

(a) The program has no problem, it reads the standard input into `bufString` and `word`, if one of the standard input is null, then break the `while` loop.

(b) `iter` cannot be both defined and get compared one expression. The correct version of (b) is like:

```cpp
vector<int>::iterator iter = ivec.begin();
while (iter != ivec.end()) {
    // do something...
    ++iter;
}
```

(c) The `while` loop will be executed forever since `ptr = 0` always yields a `true` result. The correct form might be:

```cpp
while (ptr == 0) {
    ptr = find_a_value();
}
```

(d) Variable `status` cannot be used outside of the `while` loop, we don't have to judge `status` because it will always be false when the code get out of the `while` loop. Possible answer:

```cpp
while (bool status = find(word)) {
    word = get_next_word();
}
cout << "Did not find any words\n";
```