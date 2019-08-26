# Exercise 12.13

Extend your version of the `Screen` class to include the `move`, `set`, and `display` operations. Test your class by executing the expression:

```cpp
[View full width]
// move cursor to given position, set that character and display the screen
myScreen.move(4,0).set('#').display(cout);
```

**Answer**:

```cpp
// Screen.h
#include <iostream>
#include <string>

class Screen {
public:
    typedef std::string::size_type index;
    Screen (index h, index w)
    {
        height = h;
        width = w;
        contents = std::string(h * w, '0');
    }
    // interface member functions
    // display overloaded on whether the object is const or not 
    Screen& display(std::ostream &os)
    {
        do_display(os);
        return *this;
    }
    const Screen& display(std::ostream &os) const
    {
        do_display(os);
        return *this;
    }
    Screen& set(char);
    Screen& move(index, index);
private:
    std::string contents;
    index cursor;
    index height, width;
    // single function to do the work of displaying a Screen, 
    // will be called by the display operations
    // as before
    void do_display(std::ostream &os) const;
};
```

```cpp
// Screen.cc
#include "Screen.h"

Screen& Screen::set(char c)
{
    contents[cursor] = c;
    return *this;
}

Screen& Screen::move(index r, index c)
{
    index row = r * width; // row location
    cursor = row + c;
    return *this;
}

void Screen::do_display(std::ostream &os) const
{
    for (int r = 0; r < height; ++r) {
        for (int c = 0; c < width; ++c) {
            os << contents[r * width + c];
        }
        os << '\n';
    }
    // os << contents;
}
```

```cpp
// screen_program.cc
#include "Screen.h"
using namespace std;

int main()
{
    Screen myScreen(5, 5);
    myScreen.move(4,0).set('#').display(cout);
    return 0;
}
```
