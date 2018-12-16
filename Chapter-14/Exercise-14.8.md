# Exercise 14.8

In the exercises to Section 12.4 (p. 451 ) you wrote a sketch of one of the following classes:

(a) `Book` (b) `Date` (c) `Employee` (d) `Vehicle` (e) `Object` (f) `Tree`

Write the output operator for the class you chose.

**Answer**:

To see the definition of the class I chose, please see [this](../Chapter-12/Exercise-12.20).

```cpp
std::ostream& operator<<(std::ostream &out, Vehicle &v)
{
    out << wheel_num << "\t"
        << need_gas << "\t"
        << door_num << "\t"
        << brand << "\t";
    return out;
}
```