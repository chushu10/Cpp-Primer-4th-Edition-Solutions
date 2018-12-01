# Best Practices

- Unless you intend to use the default initial value of the container elements, it is more efficient to allocate an empty container and add elements as the values for those elements become known.
- A copy constructor is synthesized even if we define other constructors.
- If a class has a member that is an array, then the synthesized copy constructor will copy the array. It does so by *copying each element*.
- It is legal to declare but not define a member function.
- If a class needs a copy constructor, it will also need an assignment operator.