#include <stdio.h>

int main() {
    int n, i;
    int a=0, b=1, c;
    printf("Enter the number of Fibonacci terms to display: ");
    scanf("%d", &n);

    for(i=0; i<n; i++) {
        printf("%d ", a);

        c = a + b;
        a = b;
        b = c;
    }

    return 0;
}
# OUTPUT
<img width="354" height="158" alt="image" src="https://github.com/user-attachments/assets/c8f34eea-4514-48a1-b623-a2d562d79386" />

