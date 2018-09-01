# Exercise 7.26

Write a version of `make_plural` with a default argument of 's'. Use that version to print singular and plural versions of the words "success" and "failure".

**Answer**:

```cpp
void make_plural(const string& word, char s = 's') {
    if (word[word.size() - 1] == 's') {
        cout << word + "es";
    } else {
        cout << word + s;
    }
}
```