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
#OUTPUT
<img width="279" height="135" alt="Screenshot 2026-08-21 143738" src="https://github.com/user-attachments/assets/6505191a-3397-4999-94fd-2faa2cc18f9b" />

