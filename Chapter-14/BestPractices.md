# Best Practices

- Generally, output operators should print the contents of the object, with minimal formatting. They should not print a newline.
- IO operators usually read or write the non`public` data members. As a consequence, classes often make the IO operators `friend`s.