

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.

Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};
struct Node* head = NULL;
void push(int value) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = value;
    new_node->next = head;
    head = new_node;
}
void display() {
    struct Node* p = head;
    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Stack elements:\n");
    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}
void pop() {
    if (head == NULL) {
        printf("Stack underflow.\n");
        return;
    }
    struct Node* temp = head;
    head = head->next;
    free(temp);
}
int main() {
    int choice, value;
    while (1) {
        printf("\n1. Push\n2. Pop\n3. Display\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
        case 1:
            printf("Enter value to push: ");
            scanf("%d", &value);
            push(value);
            break;
        case 2:
            pop();
            break;
        case 3:
            display();
            break;
        case 4:
            exit(0);
        default:
            printf("Invalid choice.\n");
        }
    }
    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/356fa143-59ed-4c36-b6c2-edf3b6f3fbe8)


Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};
struct Node* head = NULL;
void push(int value) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = value;
    new_node->next = head;
    head = new_node;
    printf("Pushed %d onto stack.\n", value);
}
void pop() {
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    struct Node* temp = head;
    printf("Popped element: %d\n", temp->data);
    head = head->next;
    free(temp);
}
void display() {
    struct Node* current = head;
    if (current == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Stack elements:\n");
    while (current != NULL) {
        printf("%d\n", current->data);
        current = current->next;
    }
}
int main() {
    int choice, value;
    while (1) {
        printf("\n1. Push\n2. Pop\n3. Display\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
        case 1:
            printf("Enter value to push: ");
            scanf("%d", &value);
            push(value);
            break;
        case 2:
            pop();
            break;
        case 3:
            display();
            break;
        case 4:
            exit(0);
        default:
            printf("Invalid choice.\n");
        }
    }
    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/046d2235-44c4-4f36-bf0e-169120357f15)



Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};
struct Node* front = NULL;
struct Node* rear = NULL;
void enqueue(int value) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = value;
    new_node->next = NULL;
    if (rear == NULL) {
        front = rear = new_node;
    } else {
        rear->next = new_node;
        rear = new_node;
    }
    printf("Enqueued %d\n", value);
}
void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    struct Node* temp = front;
    printf("Queue elements:\n");
    while (temp != NULL) {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}
void dequeue() {
    if (front == NULL) {
        printf("Queue is empty. Cannot dequeue.\n");
        return;
    }
    struct Node* temp = front;
    printf("Dequeued %d\n", front->data);
    front = front->next;

    if (front == NULL) {
        rear = NULL;
    }
    free(temp);
}
int main() {
    int choice, value;
    while (1) {
        printf("\n1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
        case 1:
            printf("Enter value to enqueue: ");
            scanf("%d", &value);
            enqueue(value);
            break;
        case 2:
            dequeue();
            break;
        case 3:
            display();
            break;
        case 4:
            exit(0);
        default:
            printf("Invalid choice.\n");
        }
    }
    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/857c5ca3-cdb2-4717-8e3f-919432e8aee0)

Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};
struct Node* front = NULL;
struct Node* rear = NULL;
void enqueue(int value) {
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    if (p == NULL) {
        printf("Memory allocation failed.\n");
        return;
    }
    p->data = value;
    p->next = NULL;
    if (rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
    printf("Enqueued %d\n", value);
}
void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    struct Node* temp = front;
    printf("Queue elements:\n");
    while (temp != NULL) {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}
int main() {
    int choice, value;
    while (1) {
        printf("\n1. Enqueue\n2. Display\n3. Exit\nEnter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
        case 1:
            printf("Enter value to enqueue: ");
            scanf("%d", &value);
            enqueue(value);
            break;
        case 2:
            display();
            break;
        case 3:
            exit(0);
        default:
            printf("Invalid choice.\n");
        }
    }
    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/a65f94d4-518f-45ca-8bc1-5668cac22f7b)

Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};
struct Node* front = NULL;
struct Node* rear = NULL;
void enqueue(int value) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = value;
    new_node->next = NULL;
    if (rear == NULL) {
        front = rear = new_node;
    } else {
        rear->next = new_node;
        rear = new_node;
    }
    printf("Enqueued %d\n", value);
}
void peek() {
    if (front == NULL) {
        printf("Queue is empty. Cannot peek.\n");
        return;
    }
    printf("Front element (peek): %d\n", front->data);
}
void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    struct Node* temp = front;
    printf("Queue elements:\n");
    while (temp != NULL) {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}
int main() {
    int choice, value;
    while (1) {
        printf("\n1. Enqueue\n2. Peek\n3. Display\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
        case 1:
            printf("Enter value to enqueue: ");
            scanf("%d", &value);
            enqueue(value);
            break;
        case 2:
            peek();
            break;
        case 3:
            display();
            break;
        case 4:
            exit(0);
        default:
            printf("Invalid choice.\n");
        }
    }
    return 0;
}

```
Output:

![image](https://github.com/user-attachments/assets/75309414-6356-4b3c-af83-8b929f5973e9)



Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


