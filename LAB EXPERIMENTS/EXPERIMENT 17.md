## PROGRAM
``` C
#include <stdio.h>

int a[20];

void merge(int low, int mid, int high) {
    int temp[20];
    int i = low;
    int j = mid + 1;
    int k = 0;

    while(i <= mid && j <= high) {

        if(a[i] < a[j])
            temp[k++] = a[i++];

        else
            temp[k++] = a[j++];
    }

    while(i <= mid)
        temp[k++] = a[i++];

    while(j <= high)
        temp[k++] = a[j++];

    for(i = low, k = 0; i <= high; i++, k++)
        a[i] = temp[k];
}

void mergeSort(int low, int high) {

    int mid;

    if(low < high) {

        mid = (low + high) / 2;

        mergeSort(low, mid);
        mergeSort(mid + 1, high);

        merge(low, mid, high);
    }
}

int main() {
    int n, i;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter array: ");

    for(i = 0; i < n; i++)
        scanf("%d", &a[i]);

    mergeSort(0, n - 1);

    printf("Sorted array: ");

    for(i = 0; i < n; i++)
        printf("%d ", a[i]);

    return 0;
}

```
# OUTPUT
<img width="340" height="155" alt="image" src="https://github.com/user-attachments/assets/4da0e696-bea7-47eb-b9c2-ccd1eb6cdbeb" />

