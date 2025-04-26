EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

#include <stdio.h>
int stack[100];  
int top = -1;
int max;         
void display() {
    if(top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements are:\n");
        for(int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}
void push(int value) {
    if(top == max - 1) {
        printf("Stack overflow! Cannot push %d\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%d pushed onto stack.\n", value);
    }
}
void pop() {
    if(top == -1) {
        printf("Stack underflow! Cannot pop.\n");
    } else {
        printf("%d popped from stack.\n", stack[top]);
        top--;
    }
}



Output:
Enter your choice: 3
Stack elements are:
20
10


Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

#include <stdio.h>
int stackSize;
int top = -1;
float stack[100]; 
void push(float value) {
    if(top == stackSize - 1) {
        printf("Stack overflow! Cannot push %.2f\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%.2f pushed onto stack.\n", value);
    }
}
int main() {
    int n, i;
    float value;
    printf("Enter the size of the stack (up to 100): ");
    scanf("%d", &stackSize);
    if(stackSize <= 0 || stackSize > 100) {
        printf("Invalid size! Please restart the program.\n");
        return 1;
    }
    printf("Enter the number of elements you want to push: ");
    scanf("%d", &n);
    if(n > stackSize) {
        printf("Cannot push more elements than the stack size!\n");
        return 1;
    }
    for(i = 0; i < n; i++) {
        printf("Enter value %d: ", i + 1);
        scanf("%f", &value);
        push(value);
    }
    return 0;
}


Output:

Enter the size of the stack (up to 100): 5
Enter the number of elements you want to push: 3
Enter value 1: 10.5
10.50 pushed onto stack.
Enter value 2: 20.75
20.75 pushed onto stack.
Enter value 3: 30.25
30.25 pushed onto stack.




Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

int rear;
int front;
int i;
float queue[50];
void display()
{
    if(rear==-1 && front==-1)
    {
        printf("No elements to display");
    }
    else
    {
        for(i=front;i<=rear;i++)
        {
            printf("%.1f ",queue[i]);
        }
    }
}

Output:

rear=-1;
front=-1;
enqueue(100.5);
enqueue(200.5);
enqueue(300.5);
display();
100.5 200.5 300.5

Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

#include <stdio.h>
int size;
int front = -1;
int rear = -1;
float queue[100]; 
void enqueue(float value) {
    if(rear == size - 1) {
        printf("Queue overflow! Cannot insert %.2f\n", value);
    } else {
        if(front == -1) front = 0; 
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into queue.\n", value);
    }
}
int main() {
    int n, i;
    float value;
    printf("Enter the size of the queue (up to 100): ");
    scanf("%d", &size);
    if(size <= 0 || size > 100) {
        printf("Invalid size! Please restart the program.\n");
        return 1;
    }
    printf("Enter the number of elements you want to insert: ");
    scanf("%d", &n);
    if(n > size) {
        printf("Cannot insert more elements than the queue size!\n");
        return 1;
    }
    for(i = 0; i < n; i++) {
        printf("Enter value %d: ", i + 1);
        scanf("%f", &value);
        enqueue(value);
    }
    return 0;
}

Output:

Enter the size of the queue (up to 100): 5
Enter the number of elements you want to insert: 3
Enter value 1: 10.5
10.50 inserted into queue.
Enter value 2: 20.75
20.75 inserted into queue.
Enter value 3: 30.25
30.25 inserted into queue.


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

#include <stdio.h>
int queue[100];
int front = -1;
int rear = -1;
int size;
void dequeue() {
    if(front == -1) {
        printf("Queue is empty. Cannot delete.\n");
    } else {
        printf("%.2f deleted from queue.\n", queue[front]);
        front++;
        if(front > rear) {
            front = rear = -1; 
        }
    }
}
void enqueue(float value) {
    if(rear == size - 1) {
        printf("Queue overflow! Cannot insert %.2f\n", value);
    } else {
        if(front == -1) front = 0;
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into queue.\n", value);
    }
}
void display() {
    if(front == -1) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements are: ");
        for(int i = front; i <= rear; i++) {
            printf("%.2f ", queue[i]);
        }
        printf("\n");
    }
}
int main() {
    int n, i, choice;
    float value;
    printf("Enter the size of the queue (up to 100): ");
    scanf("%d", &size);
    if(size <= 0 || size > 100) {
        printf("Invalid size! Please restart the program.\n");
        return 1;
    }
    while(1) {
        printf("\n--- Queue Operations ---\n");
        printf("1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch(choice) {
            case 1:
                printf("Enter a float value to insert: ");
                scanf("%f", &value);
                enqueue(value);
                break;
            case 2:
                dequeue();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("Exiting...\n");
                return 0;
            default:
                printf("Invalid choice! Try again.\n");
        }
    }
}


Output:

Enter your choice: 1
Enter a float value to insert: 10.5
10.50 inserted into queue.


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
