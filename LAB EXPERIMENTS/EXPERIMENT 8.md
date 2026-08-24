## PROGRAM
``` C
#include <stdio.h>

int main() {
    int a[20], n, x, i, found = 0;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter the array: ");
    for(i = 0; i < n; i++)
        scanf("%d", &a[i]);

    printf("Enter element to search: ");
    scanf("%d", &x);

    for(i = 0; i < n; i++) {
        if(a[i] == x) {
            printf("Element found at position %d", i + 1);
            found = 1;
            break;
        }
    }

    if(found == 0)
        printf("Element not found");

    return 0;
}
```
# OUTPUT

<img width="301" height="159" alt="image" src="https://github.com/user-attachments/assets/fa1bd1d1-6470-48a0-b653-b9de048dd8f7" />

