EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

//type your code here
#include <stdio.h>
#include <stdlib.h>

// Define the structure of a node
struct Node {
    char data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to search for a character in the linked list
void search(struct Node* head, char key) {
    struct Node* current = head;
    int position = 1;
    int found = 0;

    while (current != NULL) {
        if (current->data == key) {
            printf("Element '%c' found at position %d\n", key, position);
            found = 1;
            break;
        }
        current = current->next;
        position++;
    }

    if (!found) {
        printf("Element '%c' not found in the list.\n", key);
    }
}

// Function to display the linked list (optional)
void display(struct Node* head) {
    struct Node* current = head;
    printf("Linked List: ");
    while (current != NULL) {
        printf("%c -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;

    // Manually creating a linked list: A -> B -> C -> D
    head = createNode('A');
    head->next = createNode('B');
    head->next->next = createNode('C');
    head->next->next->next = createNode('D');

    display(head);

    char key;
    printf("Enter the character to search: ");
    scanf(" %c", &key); // Notice the space before %c to consume newline
    search(head, key);

    return 0;
}


Output:

//paste your output here
Linked List: A -> B -> C -> D -> NULL
Enter the character to search: C
Element 'C' found at position 3



Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

//type your code here
#include <stdio.h>
#include <stdlib.h>

// Define the structure of a node
struct Node {
    char data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a new node at the end of the linked list
void insert(struct Node** head, char data) {
    struct Node* newNode = createNode(data);

    if (*head == NULL) {
        *head = newNode;
    } else {
        struct Node* temp = *head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }

    printf("Inserted '%c' into the linked list.\n", data);
}

// Function to display the linked list
void display(struct Node* head) {
    printf("Linked List: ");
    while (head != NULL) {
        printf("%c -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;
    int n;
    char value;

    printf("Enter the number of nodes to insert: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter character for node %d: ", i + 1);
        scanf(" %c", &value); // space before %c to handle newline
        insert(&head, value);
    }

    display(head);

    return 0;
}


Output:

//paste your output here
Enter the number of nodes to insert: 3
Enter character for node 1: A
Inserted 'A' into the linked list.
Enter character for node 2: B
Inserted 'B' into the linked list.
Enter character for node 3: C
Inserted 'C' into the linked list.
Linked List: A -> B -> C -> NULL


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

//type your code here
#include <stdio.h>
#include <stdlib.h>

// Define the structure of a doubly linked list node
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node at the end of the doubly linked list
void insertEnd(struct Node** head, int data) {
    struct Node* newNode = createNode(data);

    if (*head == NULL) {
        *head = newNode;
    } else {
        struct Node* temp = *head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
        newNode->prev = temp;
    }
}

// Function to traverse and print the doubly linked list
void traverse(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List (Forward): ");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;
    int n, value;

    printf("Enter the number of nodes to insert: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter data for node %d: ", i + 1);
        scanf("%d", &value);
        insertEnd(&head, value);
    }

    // Traverse the doubly linked list
    traverse(head);

    return 0;
}



Output:

//paste your output here
Enter the number of nodes to insert: 3
Enter data for node 1: 10
Enter data for node 2: 20
Enter data for node 3: 30
Doubly Linked List (Forward): 10 <-> 20 <-> 30 <-> NULL



Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

//type your code here
#include <stdio.h>
#include <stdlib.h>

// Define the structure of a doubly linked list node
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a new element at the end of the doubly linked list
void insertEnd(struct Node** head, int data) {
    struct Node* newNode = createNode(data);

    if (*head == NULL) {
        *head = newNode; // List is empty, new node becomes the head
    } else {
        struct Node* temp = *head;

        // Traverse to the last node
        while (temp->next != NULL) {
            temp = temp->next;
        }

        // Insert the new node at the end
        temp->next = newNode;
        newNode->prev = temp;
    }

    printf("Element %d inserted at the end of the doubly linked list.\n", data);
}

// Function to traverse and print the doubly linked list
void traverse(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List (Forward): ");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;
    int n, value;

    printf("Enter the number of nodes to insert: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter data for node %d: ", i + 1);
        scanf("%d", &value);
        insertEnd(&head, value);
    }

    // Traverse the doubly linked list
    traverse(head);

    return 0;
}


Output:

//paste your output here
Enter the number of nodes to insert: 3
Enter data for node 1: 10
Element 10 inserted at the end of the doubly linked list.
Enter data for node 2: 20
Element 20 inserted at the end of the doubly linked list.
Enter data for node 3: 30
Element 30 inserted at the end of the doubly linked list.
Doubly Linked List (Forward): 10 <-> 20 <-> 30 <-> NULL



Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




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

//type your code here
#include <stdio.h>
#include <stdlib.h>

// Define the structure of a node in the linked list
struct Node {
    int data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to delete a given element from the linked list
void deleteElement(struct Node** head, int value) {
    // Check if the linked list is empty
    if (*head == NULL) {
        printf("The linked list is empty.\n");
        return;
    }

    struct Node* temp = *head;
    struct Node* prev = NULL;

    // Case 1: The element to be deleted is the head node
    if (temp != NULL && temp->data == value) {
        *head = temp->next;  // Move the head to the next node
        free(temp);  // Free the memory of the node
        printf("Element %d deleted from the list.\n", value);
        return;
    }

    // Case 2: The element to be deleted is not the head node
    while (temp != NULL && temp->data != value) {
        prev = temp;
        temp = temp->next;
    }

    // If the element is not found
    if (temp == NULL) {
        printf("Element %d not found in the list.\n", value);
        return;
    }

    // Case 3: Deleting the node in the middle or at the end
    prev->next = temp->next;  // Link the previous node to the next of the current node
    free(temp);  // Free the memory of the node
    printf("Element %d deleted from the list.\n", value);
}

// Function to traverse and print the linked list
void traverse(struct Node* head) {
    struct Node* temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;
    int n, value;

    // Inserting some elements into the list for testing
    head = createNode(10);
    head->next = createNode(20);
    head->next->next = createNode(30);
    head->next->next->next = createNode(40);

    printf("Initial list:\n");
    traverse(head);

    // Taking user input to delete an element
    printf("Enter the element to delete: ");
    scanf("%d", &value);
    deleteElement(&head, value);

    // Display the list after deletion
    printf("Updated list:\n");
    traverse(head);

    return 0;
}


Output:

//paste your output here
Initial list:
Linked List: 10 -> 20 -> 30 -> 40 -> NULL
Enter the element to delete: 30
Element 30 deleted from the list.
Updated list:
Linked List: 10 -> 20 -> 40 -> NULL






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





