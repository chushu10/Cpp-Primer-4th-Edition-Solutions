# Exercise 8.12

In the `open_file` function, explain what the effect would be if the program failed to execute the `close`.

**Answer**:

If the `close` fails, then the following `open` call will detect that the stream is already open. If it is open, then it sets its internal state to indicate that a failure has happened. Subsequent attempts to use the file stream will fail (Section 8.4.1, p. 293).