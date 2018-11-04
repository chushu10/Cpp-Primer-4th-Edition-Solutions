# Exercise 11.10

The library defines a `find_if` function. Like find, the `find_if` function takes a pair of iterators that indicates a range over which to operate. Like `count_if`, it also takes a third parameter that names a predicate that can be used to test each element in the range. `find_if` returns an iterator that refers to the first element for which the function returns a nonzero value. It returns its second iterator argument if there is no such element. Use the `find_if` function to rewrite the portion of our program that counted how many words are greater than length six.

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
    vector<string>::iterator it = words.begin();
    vector<string>::size_type wc = 0;
    while (it != words.end()) {
        it = find_if(it, words.end(), GT4) + 1;
        wc++;
    }
    cout << wc << " " << make_plural(wc, "word", "s")
         << " 6 characters or longer" << endl;

    return 0;
}

// the quick red fox jumps over the slow red turtle
```