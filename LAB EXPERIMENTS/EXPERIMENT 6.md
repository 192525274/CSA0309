## PROGRAM
``` C
#include <stdio.h>

int fib(int n) {
    if(n <= 1)
        return n;

    return fib(n-1) + fib(n-2);
}

int main() {
    int n, i;
    printf("enter the number of terms :");
    scanf("%d", &n);
    printf("fibonacci series=");

    for(i=0; i<n; i++)
        printf("%d ", fib(i));

    return 0;
}
```
# OUTPUT

<img width="304" height="155" alt="image" src="https://github.com/user-attachments/assets/fa0b4431-c934-4473-a64a-38d9e644ab0b" />

