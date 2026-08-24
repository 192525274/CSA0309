## PROGRAM
``` C
#include <stdio.h>

struct edge {
    int u;
    int v;
    int weight;
};

int parent[20];

int find(int x) {

    while(parent[x] != x)
        x = parent[x];

    return x;
}

int main() {

    struct edge e[20], temp;

    int n, m;
    int i, j;
    int a, b;
    int count = 0;
    int cost = 0;

    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter number of edges: ");
    scanf("%d", &m);

    printf("Enter each edge as: source destination weight\n");

    for(i = 0; i < m; i++) {

        printf("Edge %d: ", i + 1);

        scanf("%d%d%d",
              &e[i].u,
              &e[i].v,
              &e[i].weight);
    }

    for(i = 0; i < n; i++)
        parent[i] = i;

    /* Sort edges by weight */

    for(i = 0; i < m - 1; i++) {

        for(j = i + 1; j < m; j++) {

            if(e[i].weight > e[j].weight) {

                temp = e[i];
                e[i] = e[j];
                e[j] = temp;
            }
        }
    }

    printf("\nEdges in Minimum Spanning Tree:\n");

    for(i = 0; i < m && count < n - 1; i++) {

        a = find(e[i].u);
        b = find(e[i].v);

        if(a != b) {

            printf("%d - %d = %d\n",
                   e[i].u,
                   e[i].v,
                   e[i].weight);

            cost = cost + e[i].weight;

            parent[a] = b;

            count++;
        }
    }

    printf("Minimum cost = %d\n", cost);

    return 0;
}
```
# OUTPUT
<img width="352" height="212" alt="image" src="https://github.com/user-attachments/assets/08896403-3ca2-4d49-929f-f387044c9814" />

