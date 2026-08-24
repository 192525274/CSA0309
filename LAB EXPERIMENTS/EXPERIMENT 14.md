## PROGRAM
``` C
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *left;
    struct node *right;
};

struct node* create(int value) {
    struct node *newnode;

    newnode = (struct node*)malloc(sizeof(struct node));

    newnode->data = value;
    newnode->left = NULL;
    newnode->right = NULL;

    return newnode;
}

struct node* insert(struct node *root, int value) {

    if(root == NULL)
        return create(value);

    if(value < root->data)
        root->left = insert(root->left, value);

    else
        root->right = insert(root->right, value);

    return root;
}

void inorder(struct node *root) {
    if(root != NULL) {
        inorder(root->left);
        printf("%d ", root->data);
        inorder(root->right);
    }
}

void preorder(struct node *root) {
    if(root != NULL) {
        printf("%d ", root->data);
        preorder(root->left);
        preorder(root->right);
    }
}

void postorder(struct node *root) {
    if(root != NULL) {
        postorder(root->left);
        postorder(root->right);
        printf("%d ", root->data);
    }
}

int main() {
    struct node *root = NULL;
    int n, i, value;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    printf("Enter node values: ");

    for(i = 0; i < n; i++) {
        scanf("%d", &value);
        root = insert(root, value);
    }

    printf("\nInorder: ");
    inorder(root);

    printf("\nPreorder: ");
    preorder(root);

    printf("\nPostorder: ");
    postorder(root);

    return 0;
}
```
# OUTPUT
<img width="286" height="95" alt="image" src="https://github.com/user-attachments/assets/b3ac9d11-2944-4d2e-a244-fffa145e70b9" />

