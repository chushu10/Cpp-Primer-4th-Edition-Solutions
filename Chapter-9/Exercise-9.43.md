# Exercise 9.43

Use a `stack` to process parenthesized expressions. When you see an open parenthesis, note that it was seen. When you see a close parenthesis after an open parenthesis, `pop` elements down to and including the open parenthesis off the `stack`. `push` a value onto the stack to indicate that a parenthesized expression was replaced.

**Answer**:

```cpp
#include <stack>
#include <iostream>
#include <string>
using namespace std;

int main(int argc, char const *argv[])
{
    string expressions("sfdsfsd(344dkfdl)sdfdfdf(fe9fjklsek)sfsdfsdf(jfksl)");
    stack<char> charStack;
    bool reading;
    for (size_t i = 0; i != expressions.size(); ++i) {
        if (expressions.at(i) == ')') {
            cout << "Read a expression: (";
            while (charStack.top() != '(') {
                cout << charStack.top();
                charStack.pop();
            }
            cout << ")" << endl;
            charStack.pop(); // pop '('
            charStack.push('#'); // replaced
            reading = false;
            continue;
        }
        if (expressions.at(i) == '(') {
            cout << "Start reading" << endl;
            reading = true;
            charStack.push(expressions.at(i));
            continue;
        }
        if (reading) {
            charStack.push(expressions.at(i));
            continue;
        }
    }
    cout << charStack.size() << " expressions are read." << endl;
    return 0;
}
```