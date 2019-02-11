# Exercise 15.10

In the exercises to Section 15.2.1 (p. 562 ) you wrote a base class to represent the lending policies of a library. Assume the library offers the following kinds of lending materials, each with its own check-out and check-in policy. Organize these items into an inheritance hierarchy:

- record
- video
- rental book
- book
- children's puppet
- cdrom book
- sony play station video game
- audio book
- sega video game
- nintendo video game

**Answer**:

```bash
      record
     /      \
audio book  video
               \
            video game
            /   |   \
       sony   sega  nintendo

           book
          /   \
rental book   cdrom book
```