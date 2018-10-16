# Exercise 9.39

Write a program that, given the `string`s

```cpp
string line1 = "We were her pride of 10 she named us:";
string line2 = "Benjamin, Phoenix, the Prodigal";
string line3 = "and perspicacious pacific Suzanne";
string sentence = line1 + ' ' + line2 + ' ' + line3;
```

counts the number of words in `sentence` and identifies the largest and smallest words. If several words have the largest or smallest length, report all of them.

**Answer**:

```cpp
#include <string>
#include <iostream>
#include <sstream>
#include <vector>
using namespace std;

int main(int argc, char const *argv[])
{
    string line1 = "We were her pride of 10 she named us:";
    string line2 = "Benjamin, Phoenix, the Prodigal";
    string line3 = "and perspicacious pacific Suzanne";
    string sentence = line1 + ' ' + line2 + ' ' + line3;

    stringstream ss(sentence);
    string word;
    int count = 0;
    vector<string> largestWords;
    vector<string> smallestWords;
    string largestWord = "";
    string smallestWord = "thiswordisbiggerthananywordsinthesentence";
    while (ss >> word) {
        if (word.length() >= largestWord.length()) {
            largestWord = word;
        }
        if (word.length() <= smallestWord.length()) {
            smallestWord = word;
        }
        ++count;
    }
    stringstream ss2(sentence);
    while (ss2 >> word) {
        if (word.length() == largestWord.length()) {
            largestWords.push_back(word);
        }
        if (word.length() == smallestWord.length()) {
            smallestWords.push_back(word);
        }
    }
    cout << "There are " << count << " words in the sentence." << endl;
    cout << "Largest word(s) are: ";
    vector<string>::iterator it = largestWords.begin();
    for (; it != largestWords.end(); ++it) {
        cout << *it << " ";
    }
    cout << endl;
    cout << "Smallest word(s) are: ";
    it = smallestWords.begin();
    for (; it != smallestWords.end(); ++it) {
        cout << *it << " ";
    }
    cout << endl;
    return 0;
}
```