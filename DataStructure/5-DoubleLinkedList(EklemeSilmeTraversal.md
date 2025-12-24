#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *prev, *next;
};

struct node* head = NULL;

void insert(int val) {
    struct node* n = malloc(sizeof(struct node));
    n->data = val;
    n->prev = NULL;
    n->next = head;
    if(head) head->prev = n;
    head = n;
}

void delete(int val) {
    struct node* t = head;
    while(t && t->data!=val) t=t->next;
    if(!t) return;
    if(t->prev) t->prev->next = t->next;
    else head = t->next;
    if(t->next) t->next->prev = t->prev;
    free(t);
}

void traverse() {
    struct node* t = head;
    while(t) {
        printf("%d ", t->data);
        t=t->next;
    }
}