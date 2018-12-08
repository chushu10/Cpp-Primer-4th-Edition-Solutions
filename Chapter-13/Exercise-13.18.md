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
// ex1318.h
#include <string>
#include <set>

class Folder;

class Message {
    friend class Folder;
public:
    // folders is initialized to the empty set automatically
    Message(const std::string &str = ""): contents(str) { }
    // copy control: we must manage pointers to this Message
    // from the Folders pointed to by folders
    Message(const Message&);
    Message& operator=(const Message&);
    ~Message();
    // add/remove this Message from specified Folder's set of messages
    void save(Folder&);
    void remove(Folder&);
private:
    std::string contents; // actual message text
    std::set<Folder*> folders; // Folders that have this Message
    // Utility functions used by copy constructor, assignment, and destructor:
    // Add this Message to the Folders that point to the parameter
    void put_Msg_in_Folders(const std::set<Folder*>&);
    // Remove this Message from every Folder in folders
    void remove_Msg_from_Folders();
    // Utility functions used by Folder class
    void addFldr(Folder* fldr) { folders.insert(fldr); }
    void remFldr(Folder* fldr) { folders.erase(fldr); }
};

class Folder {
    friend class Message;
public:
    Folder(const std::string &str): name(str) { }
    Folder(const Folder&);
    Folder& operator=(const Folder&);
    ~Folder();
private:
    std::string name;
    std::set<Message*> msgs;
    void addMsg(Message* msg) { msgs.insert(msg); }
    void remMsg(Message* msg) { msgs.erase(msg); }
    void put_Fldr_in_Msgs(const std::set<Message*>&);
    void remove_Fldr_from_Msgs();
};
```

```cpp
// ex1318.cc
#include "ex1318.h"

Message::Message(const Message &m):
    contents(m.contents), folders(m.folders)
{
    // add this Message to each Folder that points to m
    put_Msg_in_Folders(folders);
}

Message& Message::operator=(const Message &rhs)
{
    if (&rhs != this) {
        remove_Msg_from_Folders(); // update existing Folders
        contents = rhs.contents;   // copy contents from rhs
        folders = rhs.folders;     // copy Folder pointers from rhs
        // add this Message to each Folder in rhs
        put_Msg_in_Folders(rhs.folders);
    }
    return *this;
}

Message::~Message()
{
    remove_Msg_from_Folders();
}

// add this Message to Folders that point to rhs
void Message::put_Msg_in_Folders(const std::set<Folder*> &rhs) {
    for(std::set<Folder*>::const_iterator beg = rhs.begin(); beg != rhs.end(); ++beg)
        (*beg)->addMsg(this); // *beg points to a Folder
}

// remove this Message from corresponding Folders
void Message::remove_Msg_from_Folders()
{
    // remove this message from corresponding folders
    for(std::set<Folder*>::const_iterator beg = folders.begin (); beg != folders.end (); ++beg)
        (*beg)->remMsg(this); // *beg points to a Folder
}

Folder::Folder(const Folder &f):
    name(f.name), msgs(f.msgs)
{
    put_Fldr_in_Msgs(msgs);
}

Folder& Folder::operator=(const Folder &f)
{
    if (&f != this) {
        remove_Fldr_from_Msgs();
        name = f.name;
        msgs = f.msgs;
        put_Fldr_in_Msgs(f.msgs);
    }
    return *this;
}

Folder::~Folder()
{
    remove_Fldr_from_Msgs();
}

void Folder::put_Fldr_in_Msgs(const std::set<Message*> &rhs)
{
    for(std::set<Message*>::const_iterator beg = rhs.begin();
                                           beg != rhs.end();
                                         ++beg)
    {
        (*beg)->addFldr(this);
    }
}

void Folder::remove_Fldr_from_Msgs()
{
    for(std::set<Message*>::const_iterator beg = msgs.begin();
                                           beg != msgs.end();
                                         ++beg)
    {
        (*beg)->remFldr(this);
    }
}
```