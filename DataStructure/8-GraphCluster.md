#include <stdio.h>

int visited[5]={0};

void dfs(int g[5][5], int v) {
    printf("%d ", v);
    visited[v]=1;
    for(int i=0;i<5;i++)
        if(g[v][i] && !visited[i])
            dfs(g,i);
}

int main() {
    int g[5][5]={
        {0,1,0,0,0},
        {1,0,0,0,0},
        {0,0,0,1,1},
        {0,0,1,0,1},
        {0,0,1,1,0}
    };

    for(int i=0;i<5;i++) {
        if(!visited[i]) {
            printf("Cluster: ");
            dfs(g,i);
            printf("\n");
        }
    }
}