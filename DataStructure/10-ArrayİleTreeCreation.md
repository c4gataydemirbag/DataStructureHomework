#include <stdio.h>

int main() {
    int tree[7] = {10,20,30,40,50,60,70};

    for(int i=0;i<7;i++) {
        printf("Node: %d ", tree[i]);
        if(2*i+1<7) printf("Left:%d ", tree[2*i+1]);
        if(2*i+2<7) printf("Right:%d ", tree[2*i+2]);
        printf("\n");
    }
    return 0;
}