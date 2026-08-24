## PROGRAM
``` C
#include <stdio.h>

int queue[10];
int front = -1;
int rear = -1;

void display() {
    int i;

    printf("Queue: ");

    if(front == -1) {
        printf("Empty");
    }
    else {
        for(i = front; i <= rear; i++)
            printf("%d ", queue[i]);
    }

    printf("\n");
}

int main() {
    int choice, value;

    while(1) {

        printf("\n1. Enqueue\n");
        printf("2. Dequeue\n");
        printf("3. Exit\n");

        printf("Enter your choice: ");
        scanf("%d", &choice);

        /* ENQUEUE */
        if(choice == 1) {

            if(rear == 9) {
                printf("Queue is full.\n");
            }
            else {

                printf("Enter value: ");
                scanf("%d", &value);

                if(front == -1)
                    front = 0;

                rear++;
                queue[rear] = value;

                printf("After Enqueue:\n");
                display();
            }
        }

        /* DEQUEUE */
        else if(choice == 2) {

            if(front == -1 || front > rear) {
                printf("Queue is empty.\n");
            }
            else {

                printf("Deleted value: %d\n", queue[front]);

                front++;

                if(front > rear) {
                    front = -1;
                    rear = -1;
                }

                printf("After Dequeue:\n");
                display();
            }
        }

        /* EXIT */
        else if(choice == 3) {
            break;
        }

        else {
            printf("Invalid choice.\n");
        }
    }

    return 0;
}
```
# OUTPUT
<img width="392" height="284" alt="image" src="https://github.com/user-attachments/assets/f5a85ef0-eb16-4848-a6cf-f69ba4ac94c4" />

