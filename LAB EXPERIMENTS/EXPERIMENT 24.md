## PROGRAM
``` C
#include <stdio.h>

#define INF 9999

int main() {

    int graph[10][10];
    int visited[10] = {0};

    int n, i, j;
    int min, u, v;
    int cost = 0;

    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter weighted adjacency matrix:\n");

    for(i = 0; i < n; i++)
        for(j = 0; j < n; j++)
            scanf("%d", &graph[i][j]);

    visited[0] = 1;

    printf("\nEdges in Minimum Spanning Tree:\n");

    for(i = 0; i < n - 1; i++) {

        min = INF;
        u = -1;
        v = -1;

        for(j = 0; j < n; j++) {

            if(visited[j] == 1) {

                int k;

                for(k = 0; k < n; k++) {

                    if(visited[k] == 0 &&
                       graph[j][k] != 0 &&
                       graph[j][k] < min) {

                        min = graph[j][k];
                        u = j;
                        v = k;
                    }
                }
            }
        }

        printf("%d - %d = %d\n", u, v, min);

        cost = cost + min;
        visited[v] = 1;
    }

    printf("Minimum cost = %d\n", cost);

    return 0;
}
```
# OUTPUT
<img width="336" height="179" alt="image" src="https://github.com/user-attachments/assets/43b17db3-0220-4883-bfb7-4b61e1c6ed8e" />

