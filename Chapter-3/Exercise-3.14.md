# Exercise 3.14

Read some text into a `vector`, storing each word in the input as an element in the `vector`. Transform each word into uppercase letters. Print the transformed elements from the `vector`, printing eight words to a line.

**Answer**:

```cpp
#include <iostream>
#include <string>
#include <vector>
using std::cin;
using std::cout;
using std::endl;
using std::string;
using std::vector;
int main()
{
    int num;
    string word;
    vector<string> svec;

    cout << "Please input the number of words:" << endl;
    cin >> num;

    cout << "Please input each word:" << endl;
    // 1. Read words into a vector
    for (int i = 0; i < num; i++) {
        cin >> word;
        svec.push_back(word);
    }

    // 2. Transform each word to uppercase letters
    for (vector<string>::size_type ix = 0; ix < svec.size(); ix++) {

        for (string::size_type jx = 0; jx < svec[ix].size(); jx++) {
            svec[ix][jx] = toupper(svec[ix][jx]);
        }
    }

    // 3. Print the transformed vector, 8 words a line
    for (vector<string>::size_type ix = 0; ix < svec.size(); ix++) {
        if (ix % 8 == 0) {
            cout << endl;
        }
        cout << svec[ix] << " ";
    }

    return 0;
}
```