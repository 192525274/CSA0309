## PROGRAM
``` C
#include <stdio.h>

int a[20];

void quickSort(int low, int high) {

    int i = low;
    int j = high;
    int pivot = a[(low + high) / 2];
    int temp;

    while(i <= j) {

        while(a[i] < pivot)
            i++;

        while(a[j] > pivot)
            j--;

        if(i <= j) {

            temp = a[i];
            a[i] = a[j];
            a[j] = temp;

            i++;
            j--;
        }
    }

    if(low < j)
        quickSort(low, j);

    if(i < high)
        quickSort(i, high);
}

int main() {
    int n, i;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter array: ");

    for(i = 0; i < n; i++)
        scanf("%d", &a[i]);

    quickSort(0, n - 1);

    printf("Sorted array: ");

    for(i = 0; i < n; i++)
        printf("%d ", a[i]);

    return 0;
}

```
# OUTPUT
<img width="321" height="161" alt="image" src="https://github.com/user-attachments/assets/56b478bd-e6f3-4459-b7f7-4b2399ff8f7d" />

