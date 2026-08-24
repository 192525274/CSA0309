## PROGRAM
``` C
#include <stdio.h>

int main() {
    int n, i;
    long fact = 1;

    scanf("%d", &n);

    for(i=1; i<=n; i++)
        fact = fact * i;

    printf("%ld", fact);

    return 0;
}
```
# OUTPUT
<img width="307" height="152" alt="image" src="https://github.com/user-attachments/assets/0b6a95b7-3e80-49d1-8e4c-1e56e0393fb1" />



