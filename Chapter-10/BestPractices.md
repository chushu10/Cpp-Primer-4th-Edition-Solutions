# Best Practices

- The key type needs to support only the `<` operator. There is no requirement that it support the other relational or equality operators.
- When learning the `map` interface, it is essential to remember that the `value_type` is a `pair` and that we can change the value but not the key member of that `pair`.