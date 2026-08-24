## PROGRAM
``` C
#include <stdio.h>

int main() {
    int hash[10];
    int n, i, value, position;

    for(i = 0; i < 10; i++)
        hash[i] = -1;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter elements: ");

    for(i = 0; i < n; i++) {

        scanf("%d", &value);

        position = value % 10;

        while(hash[position] != -1) {
            position = (position + 1) % 10;
        }

        hash[position] = value;
    }

    printf("\nHash Table:\n");

    for(i = 0; i < 10; i++)
        printf("Index %d : %d\n", i, hash[i]);

    return 0;
}
```
# OUTPUT
<img width="356" height="205" alt="image" src="https://github.com/user-attachments/assets/7c4f17d9-3d8b-4d5a-8e83-28002151380c" />

