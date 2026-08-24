## PROGRAM
``` C
#include <stdio.h>

int main() {
    int a[20], n, x;
    int low, high, mid, i;
    int found = 0;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter sorted array: ");
    for(i = 0; i < n; i++)
        scanf("%d", &a[i]);

    printf("Enter element to search: ");
    scanf("%d", &x);

    low = 0;
    high = n - 1;

    while(low <= high) {
        mid = (low + high) / 2;

        if(a[mid] == x) {
            printf("Element found at position %d", mid + 1);
            found = 1;
            break;
        }
        else if(x > a[mid]) {
            low = mid + 1;
        }
        else {
            high = mid - 1;
        }
    }

    if(found == 0)
        printf("Element not found");

    return 0;
}
```
# OUTPUT

<img width="293" height="142" alt="image" src="https://github.com/user-attachments/assets/b29e76f8-4e30-4996-b8e2-a8929381c132" />

