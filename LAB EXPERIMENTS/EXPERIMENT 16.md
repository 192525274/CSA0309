## PROGRAM
``` C
#include <stdio.h>

int main() {
    int a[20], n, i, j, key;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter array: ");

    for(i = 0; i < n; i++)
        scanf("%d", &a[i]);

    for(i = 1; i < n; i++) {

        key = a[i];
        j = i - 1;

        while(j >= 0 && a[j] > key) {
            a[j + 1] = a[j];
            j--;
        }

        a[j + 1] = key;
    }

    printf("Sorted array: ");

    for(i = 0; i < n; i++)
        printf("%d ", a[i]);

    return 0;
}
```
# OUTPUT
<img width="338" height="148" alt="image" src="https://github.com/user-attachments/assets/42e1bfe1-c5a7-42a3-8530-c7b1b73a4aa1" />

