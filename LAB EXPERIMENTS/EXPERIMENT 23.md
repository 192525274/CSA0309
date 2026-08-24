## PROGRAM
``` C
#include <stdio.h>

int graph[10][10];
int visited[10];
int n;

void DFS(int vertex) {

    int i;

    printf("%d ", vertex);

    visited[vertex] = 1;

    for(i = 0; i < n; i++) {

        if(graph[vertex][i] == 1 &&
           visited[i] == 0) {

            DFS(i);
        }
    }
}

int main() {

    int i, j, start;

    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter adjacency matrix:\n");

    for(i = 0; i < n; i++)
        for(j = 0; j < n; j++)
            scanf("%d", &graph[i][j]);

    printf("Enter starting vertex: ");
    scanf("%d", &start);

    printf("DFS Traversal: ");

    DFS(start);

    return 0;
}
```
# OUTPUT
<img width="406" height="187" alt="image" src="https://github.com/user-attachments/assets/4f489c68-d330-48b8-8ce6-d95a52db5c59" />

