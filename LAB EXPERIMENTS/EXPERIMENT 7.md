## PROGRAM
``` C
#include <stdio.h>

int main() {
    int a[20], n, i, pos, x, choice;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    printf("Enter the array: ");
    for(i = 0; i < n; i++)
        scanf("%d", &a[i]);

    printf("\n1. Insert\n2. Delete\n3. Display\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);

    if(choice == 1) {
        printf("Enter position: ");
        scanf("%d", &pos);

        printf("Enter element: ");
        scanf("%d", &x);

        for(i = n; i > pos; i--)
            a[i] = a[i-1];

        a[pos] = x;
        n++;

        printf("Array after insertion: ");
        for(i = 0; i < n; i++)
            printf("%d ", a[i]);
    }

    else if(choice == 2) {
        printf("Enter position to delete: ");
        scanf("%d", &pos);

        for(i = pos; i < n-1; i++)
            a[i] = a[i+1];

        n--;

        printf("Array after deletion: ");
        for(i = 0; i < n; i++)
            printf("%d ", a[i]);
    }

    else if(choice == 3) {
        printf("Array: ");
        for(i = 0; i < n; i++)
            printf("%d ", a[i]);
    }

    else {
        printf("Invalid choice");
    }

    return 0;
}
```
# OUTPUT

<img width="351" height="221" alt="image" src="https://github.com/user-attachments/assets/67188f4e-d84b-4649-a692-83d75fe0ad94" />

