#include <stdio.h>

int fact(int n) {
    if(n == 0 || n == 1)
        return 1;

    return n * fact(n-1);
}

int main() {
    int n;
    printf("Enter a number to find its factorial: ");
    scanf("%d", &n);

    printf("Factorial=%d", fact(n));

    return 0;
}
# OUTPUT
<img width="284" height="145" alt="image" src="https://github.com/user-attachments/assets/e96b4c7d-9660-44dc-87fd-73fbd17a4868" />

