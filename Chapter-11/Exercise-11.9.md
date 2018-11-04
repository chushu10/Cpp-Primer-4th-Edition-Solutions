# Exercise 11.9

Implement the program to count words of size 4 or greater, including printing the list of unique words in the input. Test your program by running it on the program's source file.

**Answer**:

```cpp
#include <algorithm>
#include <vector>
#include <string>
#include <iostream>
using namespace std;

// return plural version of word if ctr isn't 1
string make_plural(size_t ctr, const string &word,
                               const string &ending)
{
    return (ctr == 1) ? word : word + ending;
}
// comparison function to be used to sort by word length
bool isShorter(const string &s1, const string &s2)
{
    return s1.size() < s2.size();
}
// determine whether a length of a given word is 6 or more
bool GT6(const string &s)
{
    return s.size() >= 6;
}
bool GT4(const string &s)
{
    return s.size() >= 4;
}
int main() {
    vector<string> words;
    // copy contents of each book into a single vector
    string next_word;
    while (cin >> next_word) {
        // insert next book's contents at end of words
        words.push_back(next_word);
    }
    // sort words alphabetically so we can find the duplicates
    sort (words.begin(), words.end()); /* eliminate duplicate words:
                                        * unique reorders words so that each word appears once in the
                                        * front portion of words and returns an iterator one past the unique range;
                                        * erase uses a vector operation to remove the nonunique elements */
    vector<string>::iterator end_unique = unique(words.begin(), words.end());
    words.erase(end_unique, words.end());
    // sort words by size, but maintain alphabetic order for words of the same size
    stable_sort(words.begin(), words.end(), isShorter);
    vector<string>::size_type wc = count_if (words.begin(), words.end(), GT4);
    cout << wc << " " << make_plural(wc, "word", "s")
         << " 6 characters or longer" << endl;

    vector<string>::const_iterator it = words.begin();
    while (it != words.end()) {
        cout << *it++ << " ";
    }
    cout << endl;
    return 0;
}

// the quick red fox jumps over the slow red turtle
```