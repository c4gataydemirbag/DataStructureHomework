#include <stdio.h>

int main() {
    int a[3][3] = {
        {0, 0, 3},
        {4, 0, 0},
        {0, 5, 0}
    };

    int sparse[10][3];
    int k = 1;

    sparse[0][0] = 3;
    sparse[0][1] = 3;

    for(int i=0;i<3;i++) {
        for(int j=0;j<3;j++) {
            if(a[i][j] != 0) {
                sparse[k][0] = i;
                sparse[k][1] = j;
                sparse[k][2] = a[i][j];
                k++;
            }
        }
    }

    sparse[0][2] = k-1;

    printf("Row Col Val\n");
    for(int i=0;i<k;i++)
        printf("%d   %d   %d\n", sparse[i][0], sparse[i][1], sparse[i][2]);

    return 0;
}