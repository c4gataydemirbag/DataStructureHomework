#include <stdio.h>

void hanoi(int n, char src, char aux, char dest) {
    if(n == 1) {
        printf("Disk 1: %c -> %c\n", src, dest);
        return;
    }
    hanoi(n-1, src, dest, aux);
    printf("Disk %d: %c -> %c\n", n, src, dest);
    hanoi(n-1, aux, src, dest);
}

int main() {
    int n = 3;
    hanoi(n, 'A', 'B', 'C');
    return 0;
}