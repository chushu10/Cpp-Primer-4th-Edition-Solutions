# Exercise 13.18

Write the corresponding `Folder` class. That class should hold a `set<Message*>` that contains elements that point to `Message`s.

**Answer**:

```cpp
// Folder.h
#include <set>

class Message;

class Folder {
public:
    void addMsg(Message*);
    void remMsg(Message*);
private:
    std::set<Message*> messages;
};
```

```cpp
// Folder.cc
#include "Folder.h"

void Folder::addMsg(Message* msg)
{
    messages.insert(msg);
}

void Folder::remMsg(Message* msg)
{
    messages.erase(msg);
}
```