# Exercise 9.41

Write a program that, given the `string`s

```cpp
string generic1("Dear Ms Daisy:");
string generic2("MrsMsMissPeople");
```

implements the function

```cpp
string greet(string form, string lastname, string title, string::size_type pos, int length);
```

using the `replace` operations, where `lastname` replaces `Daisy` and `pos` indexes into `generic2` of `length` characters replacing `Ms`. For example, the following

```cpp
string lastName("AnnaP");
string salute = greet(generic1, lastName, generic2, 5, 4);
```

returns the `string`

```cpp
Dear Miss AnnaP:
```

**Answer**:

```cpp
#include <string>
#include <iostream>
using namespace std;

string greet(string form, string lastname, string title,
             string::size_type pos, int length)
{
    form.replace(8, 5, lastname);
    form.replace(5, 2, title, pos, length);
    return form;
}

int main(int argc, char const *argv[])
{
    string generic1("Dear Ms Daisy:");
    string generic2("MrsMsMissPeople");
    string lastName("AnnaP");
    string salute = greet(generic1, lastName, generic2, 5, 4);
    cout << salute << endl;
    salute = greet(generic1, lastName, generic2, 0, 3);
    cout << salute << endl;
    return 0;
}
```