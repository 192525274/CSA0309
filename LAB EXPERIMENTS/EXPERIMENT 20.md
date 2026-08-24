## PROGRAM
``` C
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    int height;
    struct node *left;
    struct node *right;
};

int height(struct node *root) {
    if(root == NULL)
        return 0;

    return root->height;
}

int max(int a, int b) {
    if(a > b)
        return a;
    return b;
}

struct node* create(int value) {
    struct node *newnode;

    newnode = (struct node*)malloc(sizeof(struct node));

    newnode->data = value;
    newnode->height = 1;
    newnode->left = NULL;
    newnode->right = NULL;

    return newnode;
}

struct node* rightRotate(struct node *y) {
    struct node *x = y->left;
    struct node *temp = x->right;

    x->right = y;
    y->left = temp;

    y->height = 1 + max(height(y->left),
                         height(y->right));

    x->height = 1 + max(height(x->left),
                         height(x->right));

    return x;
}

struct node* leftRotate(struct node *x) {
    struct node *y = x->right;
    struct node *temp = y->left;

    y->left = x;
    x->right = temp;

    x->height = 1 + max(height(x->left),
                         height(x->right));

    y->height = 1 + max(height(y->left),
                         height(y->right));

    return y;
}

int balance(struct node *root) {
    if(root == NULL)
        return 0;

    return height(root->left) - height(root->right);
}

/* INSERT */

struct node* insert(struct node *root, int value) {

    if(root == NULL)
        return create(value);

    if(value < root->data)
        root->left = insert(root->left, value);

    else if(value > root->data)
        root->right = insert(root->right, value);

    else
        return root;

    root->height = 1 + max(height(root->left),
                            height(root->right));

    /* LL */
    if(balance(root) > 1 &&
       value < root->left->data)
        return rightRotate(root);

    /* RR */
    if(balance(root) < -1 &&
       value > root->right->data)
        return leftRotate(root);

    /* LR */
    if(balance(root) > 1 &&
       value > root->left->data) {

        root->left = leftRotate(root->left);
        return rightRotate(root);
    }

    /* RL */
    if(balance(root) < -1 &&
       value < root->right->data) {

        root->right = rightRotate(root->right);
        return leftRotate(root);
    }

    return root;
}

/* FIND SMALLEST NODE */

struct node* minimum(struct node *root) {

    struct node *temp = root;

    while(temp->left != NULL)
        temp = temp->left;

    return temp;
}

/* DELETE */

struct node* deleteNode(struct node *root, int value) {

    struct node *temp;

    if(root == NULL)
        return root;

    if(value < root->data)
        root->left = deleteNode(root->left, value);

    else if(value > root->data)
        root->right = deleteNode(root->right, value);

    else {

        if(root->left == NULL ||
           root->right == NULL) {

            if(root->left != NULL)
                temp = root->left;
            else
                temp = root->right;

            if(temp == NULL) {
                temp = root;
                root = NULL;
            }
            else {
                *root = *temp;
            }

            free(temp);
        }

        else {

            temp = minimum(root->right);

            root->data = temp->data;

            root->right =
                deleteNode(root->right, temp->data);
        }
    }

    if(root == NULL)
        return root;

    root->height = 1 + max(height(root->left),
                            height(root->right));

    /* LL */
    if(balance(root) > 1 &&
       balance(root->left) >= 0)
        return rightRotate(root);

    /* LR */
    if(balance(root) > 1 &&
       balance(root->left) < 0) {

        root->left = leftRotate(root->left);
        return rightRotate(root);
    }

    /* RR */
    if(balance(root) < -1 &&
       balance(root->right) <= 0)
        return leftRotate(root);

    /* RL */
    if(balance(root) < -1 &&
       balance(root->right) > 0) {

        root->right = rightRotate(root->right);
        return leftRotate(root);
    }

    return root;
}

/* SEARCH */

void search(struct node *root, int value) {

    if(root == NULL) {
        printf("Element not found.\n");
        return;
    }

    if(root->data == value) {
        printf("Element found.\n");
    }

    else if(value < root->data) {
        search(root->left, value);
    }

    else {
        search(root->right, value);
    }
}

/* DISPLAY */

void display(struct node *root) {

    if(root != NULL) {
        display(root->left);
        printf("%d ", root->data);
        display(root->right);
    }
}

int main() {

    struct node *root = NULL;

    int choice, value;

    while(1) {

        printf("\n--- AVL TREE ---\n");
        printf("1. Insert\n");
        printf("2. Delete\n");
        printf("3. Search\n");
        printf("4. Exit\n");

        printf("Enter your choice: ");
        scanf("%d", &choice);

        /* INSERT */

        if(choice == 1) {

            printf("Enter value to insert: ");
            scanf("%d", &value);

            root = insert(root, value);

            printf("After insertion: ");
            display(root);
            printf("\n");
        }

        /* DELETE */

        else if(choice == 2) {

            if(root == NULL) {
                printf("Tree is empty.\n");
            }
            else {

                printf("Enter value to delete: ");
                scanf("%d", &value);

                root = deleteNode(root, value);

                printf("After deletion: ");
                display(root);
                printf("\n");
            }
        }

        /* SEARCH */

        else if(choice == 3) {

            printf("Enter value to search: ");
            scanf("%d", &value);

            search(root, value);
        }

        /* EXIT */

        else if(choice == 4) {
            break;
        }

        else {
            printf("Invalid choice.\n");
        }
    }

    return 0;
}
```
# OUTPUT
<img width="414" height="247" alt="image" src="https://github.com/user-attachments/assets/fd083702-fc87-42e2-a7f8-8be1c5b96401" />

