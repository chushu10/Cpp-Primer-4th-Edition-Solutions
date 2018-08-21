# Exercise 6.20

Write a program to read a sequence of `string`s from standard input until either the same word occurs twice in succession or all the words have been read. Use a `while` loop to read the text one word at a time. Use the `break` statement to terminate the loop if a word occurs twice in succession. Print the word if it occurs twice in succession, or else print a message saying that no word was repeated.

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