# Best Practices

| Sequential Containers |    |
| :-------------------- | :- |
| vector | Supports fast random access |
| list   | Supports fast insertion/deletion |
| deque  | Double-ended queue |

| Sequential Container Adaptors |    |
| :---------------------------- | :- |
| stack | Last in/First out stack |
| queue | First in/First out queue |
| priority_queue | Priority-managed queue |

- For reasons that shall become clear shortly, the most commonly used container constructor is the default constructor. In most programs, using the default constructor gives the best run-time performance and makes using the container easier.
- Two constraints of the type a container can hold:
  - The element type must support assignment.
  - We must be able to copy objects of the element type.
- We must separate the two closing `>` symbols with a space to indicate that these two characters represent two symbols. Without the space, `>>` is treated as a single symbol, the right shift operator, and results in a compile-time error.
- There is **no way to examine an iterator** to determine whether it has been invalidated. There is no test we can perform to detect that it has gone bad. Any use of an invalidated iterator is likely to yield a run-time error, but there is no guarantee that the program will crash or otherwise make it easy to detect the problem.
- When we add an element to a container, we do so by **copying** the element value into the container. Subsequent changes to the element in the container have no effect on the value that was copied, and vice versa.
- Inserting anywhere but at the end of a `vector` is an expensive operation.
- If we want to assign elements of a different but compatible element type and/or from a different container type, then we must use the `assign` operation. eg: `c.assign(b,e)`, where `c` is of type `vector<char*>` and `b` and `e` are iterators into `list<string>`.
- In general, unless there is a good reason to prefer another container, `vector` is usually the right one to use.
- When you are not certain which container the application should use, try to write your code so that it uses only operations common to both `vector`s and `list`s: Use iterators, not subscripts, and avoid random access to elements. By writing your programs this way, it will be easier to change the container from a `vector` to a `list` if necessary.