# Exercise 3.17

Redo the exercises from Section 3.3.2(p.96), using iterators rather than subscripts to access the elements in the `vector`.

**Answer**:

Redo exercise 3.13

```cpp
#include <iostream>
#include <vector>
using std::cin;
using std::cout;
using std::endl;
using std::vector;
int main()
{
    int num;
    int elem;
    vector<int> ivec;

    cout << "Please input number of elements of vector:" << endl;
    cin >> num;
    cout << "Please input each element:" << endl;
    for (vector<int>::size_type i = 0; i != num; ++i) {
        cin >> elem;
        ivec.push_back(elem);
    }

    cout << "Now Exercise 3.13 part one:" << endl;
    int last = *ivec.begin();
    for (vector<int>::const_iterator iter = ivec.begin();
                                     iter != ivec.end(); ++iter) {
        if (last % 2 != 0 || *iter % 2 != 0) {
            cout << "There is an odd number! Print last number " << last << endl;
        } else {
            cout << last + *iter << endl;
        }
        last = *iter;
    }

    cout << "Now Exercise 3.13 part two:" << endl;
    vector<int>::const_iterator head = ivec.begin(),
                                tail = ivec.end() - 1;
    while (head < tail) {
        cout << *head + *tail << endl;
        head++;
        tail--;
    }
    return 0;
}
```

Redo exercise 3.14

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
    for (vector<string>::iterator iter = svec.begin();
                                  iter != svec.end(); ++iter) {
        for (string::iterator siter = (*iter).begin();
                              siter != (*iter).end(); ++siter) {
            *siter = toupper(*siter);
        }
    }

    // 3. Print the transformed vector, 8 words a line
    for (vector<string>::const_iterator iter = svec.begin();
                                        iter != svec.end(); ++iter) {
        if ((iter - svec.begin()) % 8 == 0) {
            cout << endl;
        }
        cout << *iter << " ";
    }

    return 0;
}
```