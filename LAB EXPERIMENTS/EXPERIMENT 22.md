## PROGRAM
``` C
#include <stdio.h>

int main() {

    int graph[10][10];
    int queue[10];
    int visited[10] = {0};

    int n, i, j, start;
    int front = 0, rear = 0;
    int vertex;

    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter adjacency matrix:\n");

    for(i = 0; i < n; i++)
        for(j = 0; j < n; j++)
            scanf("%d", &graph[i][j]);

    printf("Enter starting vertex: ");
    scanf("%d", &start);

    queue[rear] = start;
    rear++;

    visited[start] = 1;

    printf("BFS Traversal: ");

    while(front < rear) {

        vertex = queue[front];
        front++;

        printf("%d ", vertex);

        for(i = 0; i < n; i++) {

            if(graph[vertex][i] == 1 &&
               visited[i] == 0) {

                queue[rear] = i;
                rear++;

                visited[i] = 1;
            }
        }
    }

    return 0;
}
```
# OUTPUT
<img width="374" height="194" alt="image" src="https://github.com/user-attachments/assets/c9e68ccb-925b-4643-b15b-ec900e4fd4d2" />

