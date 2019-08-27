# Exercise 16.39

Implement input and output operators for the template `Screen` class.

**Answer**:

```cpp
#include <iostream>
#include <string>

template <int hi, int wid> class Screen;
template <int hi, int wid> std::ostream& operator<<(std::ostream&, const Screen<hi, wid>&);
template <int hi, int wid> std::istream& operator>>(std::istream&, Screen<hi, wid>&);

template <int hi, int wid>
class Screen {
    friend std::ostream& operator<< <hi, wid>(std::ostream&, const Screen<hi, wid>&);
    friend std::istream& operator>> <hi, wid>(std::istream&, Screen<hi, wid>&);
public:
    typedef std::string::size_type index;
    Screen(): contents(hi * wid, '0'), height(hi), width(wid) { }
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

template <int hi, int wid>
Screen<hi, wid>& Screen<hi, wid>::set(char c)
{
    contents[cursor] = c;
    return *this;
}

template <int hi, int wid>
Screen<hi, wid>& Screen<hi, wid>::move(index r, index c)
{
    index row = r * width; // row location
    cursor = row + c;
    return *this;
}

template <int hi, int wid>
void Screen<hi, wid>::do_display(std::ostream &os) const
{
    for (index r = 0; r < height; ++r) {
        for (index c = 0; c < width; ++c) {
            os << contents[r * width + c];
        }
        os << '\n';
    }
    // os << contents;
}

template <int hi, int wid>
std::ostream& operator<<(std::ostream &os, const Screen<hi, wid> &s)
{
    for (typename Screen<hi, wid>::index r = 0; r < s.height; ++r) {
        for (typename Screen<hi, wid>::index c = 0; c < s.width; ++c) {
            os << s.contents[r * s.width + c];
        }
        os << '\n';
    }
    return os;
}

template <int hi, int wid>
std::istream& operator>>(std::istream &is, Screen<hi, wid> &s)
{
    char a;
    is >> a;
    std::string temp(hi * wid, a);
    s.contents = temp;
    return is;
}

int main()
{
    Screen<5, 6> myScreen;
    myScreen.move(4,0).set('#');
    // myScreen.display(std::cout);
    std::cout << myScreen;//<< std::endl;
    std::cin >> myScreen;
    std::cout << myScreen;
    return 0;
}
```
