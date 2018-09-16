# Best Practices

- The comma operator executes by evaluating each operand and returns its rightmost operand as its result. Therefore, the left operands are ignored.
- Using `endl` means we do not have to wonder whether output is pending(There is output that the program wrote but that has not shown up on the standard output) when a program crashes.
- Interactive systems usually should be sure that their input and output streams are tied. Doing so means that we are guaranteed that any output, which might include prompts to the user, has been written before attempting to read.
- If we reuse a file stream to read or write more than one file, we must `clear` the stream before using it to read from another file.