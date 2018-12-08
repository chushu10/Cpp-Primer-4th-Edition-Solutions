# Exercise 13.19

Add a `save` and `remove` operation to the `Message` and `Folder` classes. These operations should take a `Folder` and add (or remove) that `Folder` to (from) the set of `Folder`s that point to this `Message`. The operation must also update the `Folder` to know that it points to this `Message`, which can be done by calling `addMsg` or `remMsg`.

**Answer**:

```cpp
// ex1319.h
#include <string>
#include <set>
#include <iostream>

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
    void printFldrs();
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
    void printMsgs();
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
// ex1319.cc
#include "ex1319.h"

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

void Message::save(Folder &fldr)
{
    addFldr(&fldr);
    fldr.addMsg(this);
}

void Message::remove(Folder &fldr)
{
    remFldr(&fldr);
    fldr.remMsg(this);
}

void Message::printFldrs()
{
    std::cout << "Message ("
              << contents
              << ") added in these folders:"
              << std::endl;
    for(std::set<Folder*>::const_iterator beg = folders.begin();
                                          beg != folders.end();
                                        ++beg)
    {
        std::cout << (*beg)->name << ", ";
    }
    std::cout << std::endl;
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

void Folder::printMsgs()
{
    std::cout << "Foler ("
              << name
              << ") contains these messages:"
              << std::endl;
    for(std::set<Message*>::const_iterator beg = msgs.begin();
                                           beg != msgs.end();
                                         ++beg)
    {
        std::cout << (*beg)->contents << ", ";
    }
    std::cout << std::endl;
}
```