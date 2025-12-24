#include <stdio.h>

void heapifyMax(int a[], int n, int i) {
    int largest=i,l=2*i+1,r=2*i+2;
    if(l<n && a[l]>a[largest]) largest=l;
    if(r<n && a[r]>a[largest]) largest=r;
    if(largest!=i) {
        int t=a[i]; a[i]=a[largest]; a[largest]=t;
        heapifyMax(a,n,largest);
    }
}

void heapifyMin(int a[], int n, int i) {
    int smallest=i,l=2*i+1,r=2*i+2;
    if(l<n && a[l]<a[smallest]) smallest=l;
    if(r<n && a[r]<a[smallest]) smallest=r;
    if(smallest!=i) {
        int t=a[i]; a[i]=a[smallest]; a[smallest]=t;
        heapifyMin(a,n,smallest);
    }
}