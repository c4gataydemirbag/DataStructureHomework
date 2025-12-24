#include <stdio.h>
#include <ctype.h>

char stack[50];
int top = -1;

int precedence(char c) {
    if(c=='+'||c=='-') return 1;
    if(c=='*'||c=='/') return 2;
    return 0;
}

void push(char c) { stack[++top] = c; }
char pop() { return stack[top--]; }

int main() {
    char infix[] = "A+B*C";
    char postfix[50];
    int k=0;

    for(int i=0; infix[i]; i++) {
        char c = infix[i];
        if(isalnum(c))
            postfix[k++] = c;
        else {
            while(top!=-1 && precedence(stack[top])>=precedence(c))
                postfix[k++] = pop();
            push(c);
        }
    }

    while(top!=-1)
        postfix[k++] = pop();

    postfix[k] = '\0';
    printf("Postfix: %s\n", postfix);
    return 0;
}