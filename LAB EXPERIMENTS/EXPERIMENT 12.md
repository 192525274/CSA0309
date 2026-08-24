## PROGRAM
``` C
#include <stdio.h>
#include <ctype.h>

char stack[20];
int top = -1;

int priority(char ch) {
    if(ch == '+' || ch == '-')
        return 1;

    if(ch == '*' || ch == '/')
        return 2;

    return 0;
}

int main() {
    char infix[20];
    char ch;
    int i;

    printf("Enter infix expression: ");
    scanf("%s", infix);

    printf("Postfix expression: ");

    for(i = 0; infix[i] != '\0'; i++) {

        ch = infix[i];

        if(isalnum(ch)) {
            printf("%c", ch);
        }

        else if(ch == '(') {
            stack[++top] = ch;
        }

        else if(ch == ')') {

            while(stack[top] != '(')
                printf("%c", stack[top--]);

            top--;
        }

        else {

            while(top != -1 &&
                  priority(stack[top]) >= priority(ch)) {
                printf("%c", stack[top--]);
            }

            stack[++top] = ch;
        }
    }

    while(top != -1)
        printf("%c", stack[top--]);

    return 0;
}
```
# OUTPUT
<img width="338" height="134" alt="image" src="https://github.com/user-attachments/assets/f57bada8-3b5b-495b-831b-ad4a52491733" />

