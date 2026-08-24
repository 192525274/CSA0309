## PROGRAM
``` C
#include <stdio.h>

#define INF 9999

int main() {

    int graph[10][10];
    int distance[10];
    int visited[10] = {0};

    int n, i, j, start;
    int min, vertex;

    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter weighted adjacency matrix:\n");

    for(i = 0; i < n; i++)
        for(j = 0; j < n; j++)
            scanf("%d", &graph[i][j]);

    printf("Enter starting vertex: ");
    scanf("%d", &start);

    for(i = 0; i < n; i++)
        distance[i] = INF;

    distance[start] = 0;

    for(i = 0; i < n; i++) {

        min = INF;
        vertex = -1;

        for(j = 0; j < n; j++) {

            if(visited[j] == 0 &&
               distance[j] < min) {

                min = distance[j];
                vertex = j;
            }
        }

        if(vertex == -1)
            break;

        visited[vertex] = 1;

        for(j = 0; j < n; j++) {

            if(graph[vertex][j] != 0 &&
               distance[vertex] + graph[vertex][j]
               < distance[j]) {

                distance[j] =
                    distance[vertex] + graph[vertex][j];
            }
        }
    }

    printf("\nShortest distances:\n");

    for(i = 0; i < n; i++)
        printf("Vertex %d = %d\n", i, distance[i]);

    return 0;
}
```
# OUTPUT
<img width="338" height="198" alt="image" src="https://github.com/user-attachments/assets/3f607559-cdaa-484f-be94-f024661d0f0e" />

