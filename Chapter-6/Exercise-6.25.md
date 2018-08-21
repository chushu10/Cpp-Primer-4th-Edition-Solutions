# Exercise 6.25

Revise the program you wrote for the exercise in [Section 6.11](Exercise-6.21.md) (p. 214) to conditionally print information about its execution. For example, you might print each word that begins with an uppercase letter. Compile and run the program with debugging turned on and agin with it turned off.

**Answer**:

```cpp
// ex625.cc
// With debugging: g++ ex625.cc -o ex625
// Without debugging: g++ -D NDEBUG ex625.cc -o ex625
#include <iostream>
#include <string>
using std::string;
using std::cout;
using std::cin;
using std::endl;

int main(int argc, char const *argv[])
{
    string last_word;
    string word;
    cin >> last_word;
    while (cin >> word) {
        if (word == last_word) {
            if (isupper(word[0])) {
    #ifndef NDEBUG
    cout << "Successfully find the first dup word that begins with an uppercase letter" << endl;
    #endif
                cout << word << " occurs twice in succession" << endl;
                break;
            }
        }
        last_word = word;
    }
    if (word != last_word || !isupper(word[0])) {
        cout << "No word start with uppercase letter was repeated" << endl;
    }

    return 0;
}
```