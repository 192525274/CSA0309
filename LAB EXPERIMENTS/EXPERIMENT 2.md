## PROGRAM
``` C
#include <stdio.h>

int main() {
    int n, i, x;

    scanf("%d", &n);

    for(i=0; i<n; i++) {
        scanf("%d", &x);

        if(x % 2 == 0)
            printf("%d is Even\n", x);
        else
            printf("%d is Odd\n", x);
    }

    return 0;
}
```
# OUTPUT

<img width="332" height="188" alt="Screenshot 2026-08-21 141331" src="https://github.com/user-attachments/assets/2d5d450c-4458-44c2-b913-0c2439adef1a" />
