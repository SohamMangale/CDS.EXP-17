# EXPERIMENT - 17

## Aim :
To study and implement Linked List

## Software :
Vs Code 

## Theory :
- *LINKED LIST :*
A linked list is a dynamic data structure made up of nodes, each containing data and a reference to the next node. It allows efficient insertions and deletions without needing to shift elements, unlike arrays.<BR> Common types include singly linked lists, doubly linked lists, and circular linked lists.

### Types Of Linked List :
- *Singly Linked List* : This type consists of nodes where each node points to the next one, allowing only forward traversal. It is useful for simple lists where reverse traversal is not required.
- *Doubly Linked List* : This type features nodes with pointers to both the next and previous nodes, enabling traversal in both directions. It is ideal for scenarios that require frequent navigation forwards and backwards.
- *Circular Linked List* : In this structure, the last node points back to the first node, creating a circular arrangement. It allows for indefinite traversal and is useful for applications like circular queues and round-robin scheduling.

### Basic Operations For Linked List :
#### 1. Insertion :
- *At the Beginning* : New node becomes the head.
- *At the End* : New node is added after the last node.
- *At a Specific Position* : Insert after a specified node.

### 2. Deletion :
- *From the Beginning* : Remove the head node and update the head pointer.
- *From the End*: Traverse to the second-to-last node and remove the last node.
- *From a Specific Position* : Locate the node before the target and adjust pointers to remove the target node.

### 3. Traversal :
- *Start at Head* : Begin with the head node.
- *Visit Nodes* : Access the data in the current node.
- *Move to Next* : Follow the pointer to the next node.
- *End Condition* : Stop when the next pointer is null.

## Codes 
### 1.
```
//soham
//entc B1
//23070123084
//experiment 17
#include <iostream>
using namespace std;

class Link 
{
public:
    int data;
    Link* next;

    Link(int num) 
    {
        data = num;
        next = NULL;
    }
};

void insert_head(Link* &head, int data) 
{
    Link* new_node = new Link(data);
    new_node->next = head;
    head = new_node;
}

void disp(Link* head) 
{
    Link* temp = head;
    while (temp != NULL) 
    {
        cout << temp->data << "->";
        temp = temp->next;
    }
    cout << "NULL" << endl;
}

int main() 
{
    Link* head = NULL;
    insert_head(head, 30);
    disp(head);
    insert_head(head, 32);
    disp(head);
    insert_head(head, 36);
    disp(head);
    return 0;
}
```

### 2.
```
//soham
//entc B1
//23070123084
//experiment 17
#include <iostream>
using namespace std;

class Link 
{
public:
    int data;
    Link* next;

    Link(int num) 
    {
        data = num;
        next = NULL;
    }
};

void insert_head(Link* &head, int data) 
{
    Link* new_node = new Link(data);
    new_node->next = head;
    head = new_node;
}

void delete_head(Link* &head) 
{
    if (head != NULL) 
    {
        Link* temp = head;
        head = head->next;
        delete temp;
    }
}

void disp(Link* head) 
{
    Link* temp = head;
    while (temp != NULL) 
    {
        cout << temp->data << "->";
        temp = temp->next;
    }
    cout << "NULL" << endl;
}

int main() 
{
    Link* head = NULL;
    insert_head(head, 30);
    disp(head);
    insert_head(head, 32);
    disp(head);
    insert_head(head, 36);
    disp(head);
   
    delete_head(head);
    disp(head);
    delete_head(head);
    disp(head);
   
    return 0;
}
```

### 3.
```
//soham
//entc B1
//23070123084
//experiment 17
#include <iostream>
using namespace std;

struct Node 
{
    int data;
    Node* next;
};

void insert(Node*& head, int data) 
{
    Node* newNode = new Node();
    newNode->data = data;
    newNode->next = head;
    head = newNode;
}

void deleteNode(Node*& head, int key) 
{
    Node* temp = head;
    Node* prev = nullptr;
    if (temp != nullptr && temp->data == key) 
    {
        head = temp->next;
        delete temp;
        return;
    }
    while (temp != nullptr && temp->data != key) 
    {
        prev = temp;
        temp = temp->next;
    }
    if (temp == nullptr) return;
    prev->next = temp->next;        //update
    delete temp;
}

void display(Node* node) 
{
    while (node != nullptr) 
    {
        cout << node->data << " ";
        node = node->next;
    }
    cout << endl;
}

int main() 
{
    Node* head = nullptr;
    insert(head, 10);
    insert(head, 20);
    insert(head, 30);
    cout << "Linked List: ";
    display(head);
    deleteNode(head, 20);
    cout << "After Deletion: ";
    display(head);
    return 0;
}
```

## Outputs :
### 1.
![image](https://github.com/user-attachments/assets/22c2d38b-6e62-4d49-bc41-88294d58a002)



### 2
![image](https://github.com/user-attachments/assets/729dd4f4-d35c-4120-aa60-e092312a78b0)



### 3.
![image](https://github.com/user-attachments/assets/62119e56-2414-451a-8248-cc299273dabe)



## Conclusion :
The experiment successfully demonstrated the importance and efficiency of linked lists in C++ programming. The implementation highlighted the advantages of linked lists in terms of dynami
