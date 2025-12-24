#include <stdio.h>

int main() {
    int a[10]={1,2,3,4,5}, n=5;

    // Ekle
    int pos=2, val=99;
    for(int i=n;i>pos;i--)
        a[i]=a[i-1];
    a[pos]=val;
    n++;

    // Sil
    for(int i=pos;i<n-1;i++)
        a[i]=a[i+1];
    n--;

    for(int i=0;i<n;i++)
        printf("%d ", a[i]);

    return 0;
}