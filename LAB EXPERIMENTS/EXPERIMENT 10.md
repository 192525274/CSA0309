## PROGRAM
``` C
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

void display(struct node *head) {
    struct node *temp = head;

    printf("List: ");

    if(head == NULL) {
        printf("Empty");
    }

    while(temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }

    printf("NULL\n");
}

int main() {
    struct node *head = NULL;
    struct node *newnode, *temp;

    int choice, value;

    while(1) {

        printf("\n1. Insert\n");
        printf("2. Delete\n");
        printf("3. Exit\n");

        printf("Enter your choice: ");
        scanf("%d", &choice);

        /* INSERT */
        if(choice == 1) {

            newnode = (struct node*)malloc(sizeof(struct node));

            printf("Enter value: ");
            scanf("%d", &value);

            newnode->data = value;
            newnode->next = head;
            head = newnode;

            printf("After insertion:\n");
            display(head);
        }

        /* DELETE */
        else if(choice == 2) {

            if(head == NULL) {
                printf("List is empty.\n");
            }
            else {

                temp = head;
                head = head->next;

                printf("Deleted value: %d\n", temp->data);

                free(temp);

                printf("After deletion:\n");
                display(head);
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

<img width="392" height="284" alt="image" src="https://github.com/user-attachments/assets/ac6e3f03-020d-4bc9-8ec8-ea00cb8810ac" />

