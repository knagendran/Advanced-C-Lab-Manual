### EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.

Aim:
To write a C program to search a given element in the given linked list.

Algorithm:

1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

```
struct Node
{
    char data; 
    struct Node *next;
}*head;

void search(char data)
{
    struct Node *temp;
    temp=head;
    int loc=1,flag=0;
        while(temp!=NULL)
        {
            if(temp->data == data)
            {
                flag=1;
                break;
            }
            else
            {
                temp=temp->next;
                loc++;
            }
        }
        
    if(flag==0)
    {
        printf("Item not found");
    }
    else
    {
        printf("item %c found at location %d",data,loc);
                 
    }
}
```

Output:

![image](https://github.com/user-attachments/assets/f1bb62d2-7cf8-45af-bd70-8ade99648eca)


Result:

Thus, the program to search a given element in the given linked list is verified successfully.


 
### EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.

Aim:
To write a C program to insert a node in a linked list.

Algorithm:

1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

```
struct Node{
    float data; 
    struct Node *next;
}*head;

void insert(float data)
{
    struct Node *newnode,*temp;
    newnode=(struct Node *)malloc(sizeof(struct Node));
    newnode->data=data;
    newnode->next=NULL;
    if(head==NULL)
    {
        head=newnode;
    }
    else
    {
        temp=head;
        while(temp->next != NULL)
        {
            temp=temp->next;
        }
        temp->next=newnode;
    }
    
}
```

Output:

![image](https://github.com/user-attachments/assets/0bf31fea-039e-4194-88a4-af2aca9c5c0f)


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
### EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST

Aim:
To write a C program to traverse a doubly linked list.

Algorithm:

1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

```
struct Node
{
    struct Node *prev;
    struct Node *next;
    char data;
}*head;

void display()
{
    struct Node *temp=head;
    while(temp!=NULL)
    {
        printf("%c ",temp->data);
        temp=temp->next;
    }
}
```

Output:

![image](https://github.com/user-attachments/assets/b64beaf1-f5b0-4bcc-a11c-f6930d7b64b4)


Result:

Thus, the program to traverse a doubly linked list is verified successfully. 



### EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST

Aim:
To write a C program to insert an element in doubly linked list

Algorithm:

1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```
struct Node
{
    struct Node *prev;
    struct Node *next;
    int data;
}*head;

void insert(int data)
{
    struct Node *temp,*newnode=(struct Node*)malloc(sizeof(struct Node));
    newnode->data=data;
    newnode->next=NULL;
    newnode->prev=NULL;
    if(head==NULL)
    {
        head=newnode;
    }
    else
    {
        temp=head;
        while(temp->next!=NULL)
        {
            temp=temp->next;
        }
        temp->next=newnode;
        newnode->prev=temp;
    }
}
```

Output:

![image](https://github.com/user-attachments/assets/c0bba338-f5b3-4102-a8fd-205e92eddb1d)


Result:

Thus, the program to insert an element in doubly linked list is verified successfully.


### EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST


Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:

1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:

```
struct Node
{
    struct Node *prev;
    struct Node *next;
    int data;
}*head;

void delete()
{
    struct Node *temp;
    if(head==NULL)
    {
        printf("UNDERFLOW\n");
    }
    else if(head->next==NULL)
    {
        head=NULL;
        free(head);
        printf("node deleted\n");
    }
    else
    {
        temp=head;
        head=head->next;
        head->prev=NULL;
        free(temp);
        printf("node deleted\n");
    }
}
```

Output:

![image](https://github.com/user-attachments/assets/f6ee0fb1-1689-4e46-b193-0fe7026f2ac1)


Result:

Thus, the function that deletes a given element from a linked list is verified successfully.
