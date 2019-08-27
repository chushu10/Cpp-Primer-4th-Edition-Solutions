# Exercise 16.40

Which, if any, friends are necessary in class `Screen` to make the input and output operators work? Explain why each friend declaration, if any, was needed.

**Answer**:

```cpp
friend std::ostream& operator<< <hi, wid>(std::ostream&, const Screen<hi, wid>&);
friend std::istream& operator>> <hi, wid>(std::istream&, Screen<hi, wid>&);
```

We have to make input and output operators friends of `Screen` to let them visit `private` members of `Screen`.
