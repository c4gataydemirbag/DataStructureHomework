#include <stdio.h>

int q[10], front=0, rear=-1;
int visited[5]={0};

void bfs(int g[5][5], int start) {
    q[++rear]=start;
    visited[start]=1;

    while(front<=rear) {
        int v=q[front++];
        printf("%d ",v);
        for(int i=0;i<5;i++)
            if(g[v][i] && !visited[i]) {
                visited[i]=1;
                q[++rear]=i;
            }
    }
}