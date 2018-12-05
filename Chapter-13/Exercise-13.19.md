# Exercise 13.19

Add a `save` and `remove` operation to the `Message` and `Folder` classes. These operations should take a `Folder` and add (or remove) that `Folder` to (from) the set of `Folder`s that point to this `Message`. The operation must also update the `Folder` to know that it points to this `Message`, which can be done by calling `addMsg` or `remMsg`.

**Answer**:

```cpp
// Message.h
#include <string>
#include "Folder.h"

class Message {
public:
    // folders is initialized to the empty set automatically
    Message(const std::string &str = ""): contents (str) { }
    // copy control: we must manage pointers to this Message
    // from the Folders pointed to by folders
    Message(const Message&);
    Message& operator=(const Message&); ~Message();
    // add/remove this Message from specified Folder's set of messages
    void save(Folder&);
    void remove(Folder&);
private:
    std::string contents; // actual message text
    std::set<Folder*> folders; // Folders that have this Message
    // Utility functions used by copy constructor, assignment, and destructor:
    // Add this Message to the Folders that point to the parameter
    void put_Msg_in_Folders(const std::set<Folder*>&); // remove this Message from every Folder in folders
    void remove_Msg_from_Folders();
    void addFldr(Folder*);
    void remFldr(Folder*);
};
```

```cpp
// Message.cc
#include "Message.h"

Message::Message(const Message &m): contents(m.contents), folders(m.folders)
{
    // add this Message to each Folder that points to m
    put_Msg_in_Folders(folders);
}

Message& Message::operator=(const Message &rhs)
{
    if (&rhs != this) {
        remove_Msg_from_Folders(); // update existing Folders
        contents = rhs.contents; // copy contents from rhs
        folders = rhs.folders; // copy Folder pointers from rhs
        // add this Message to each Folder in rhs
        put_Msg_in_Folders(rhs.folders);
    }
    return *this;
}

Message::~Message()
{
    remove_Msg_from_Folders();
}

void Message::put_Msg_in_Folders(const std::set<Folder*> &rhs)
{
    for(std::set<Folder*>::const_iterator beg = rhs.begin(); beg != rhs.end(); ++beg)
        (*beg)->addMsg(this); // *beg points to a Folder
}

void Message::remove_Msg_from_Folders()
{
    // remove this message from corresponding folders
    for(std::set<Folder*>::const_iterator beg = folders.begin (); beg != folders.end (); ++beg)
        (*beg)->remMsg(this); // *beg points to a Folder
}

void Message::addFldr(Folder* folder)
{
    folders.insert(folder);
}

void Message::remFldr(Folder* folder)
{
    folders.erase(folder);
}

void Message::save(Folder& folder)
{
    folders.insert(&folder);
    folder.addMsg(this);
}

void Message::remove(Folder& folder)
{
    folders.erase(&folder);
    folder.remMsg(this);
}
```