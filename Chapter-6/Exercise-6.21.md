# Exercise 6.21

Revise the program from the last exercise in Section 6.10 (p.213) so that it looks only for duplicated words that start with an uppercase letter.

**Answer**:

```cpp
string last_word;
string word;
cin >> last_word;
while (cin >> word) {
    if (word == last_word) {
        cout << word << " occurs twice in succession" << endl;
        break;
    }
    last_word = word;
}
if (word != last_word) {
    cout << "No word was repeated" << endl;
}
```