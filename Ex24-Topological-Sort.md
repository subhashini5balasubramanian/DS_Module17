# Ex24 Topological Sort

## AIM:
To compose the code to determine whether the topological ordering for the following graph is possible or not.

![image](https://github.com/user-attachments/assets/c74a7111-9b59-475c-aad4-9baf23d50ec0)


## Algorithm
1. Start and create the graph using create_graph().
2. Calculate indegrees; enqueue vertices with indegree 0.
3. Initialize count and process vertices from the queue.
4. For each vertex, dequeue, add to topo_order, update adjacent vertices' indegrees, and enqueue if indegree becomes 0.
5. If a cycle exists, print error; else, print topological order and end.

## Program:
```
/*
Program to determine whether the topological ordering for the following graph is possible or not
Developed by: SUBHASHINI .B 
RegisterNumber: 212223040211
*/
//#include<stdio.h>
//#include<stdlib.h>
//#define MAX5
//int n; /*Number ofverticesinthegraph*/
//int adj[MAX][MAX];/*AdjacencyMatrix*/
//void create_graph();
//int queue[MAX], front =-1,rear =-1;
//void insert_queue(int v);
//int delete_queue();
//int isEmpty_queue();
//int indegree(int v);
int main()
{
int i,v,count,topo_order[MAX],indeg[MAX];
create_graph();
/*Find the indegreeofeachvertex*/
for(i=0;i<n;i++)
{
indeg[i]=indegree(i);
if( indeg[i] == 0 )
insert_queue(i);
}
count =0;
while( !isEmpty_queue()&&count <n)
{
v= delete_queue();
topo_order[++count]= v;/*Add vertex vto topo_order array*/
/*Delete alledgesgoing fromvertexv*/
for(i=0; i<n; i++)
{
if(adj[v][i]==1)
{
adj[v][i] = 0;
indeg[i]=indeg[i]-1;
if(indeg[i] == 0)
insert_queue(i);
}
}
}
if( count <n)
{
printf("No topologicalordering possible, graphcontains cycle\n");
exit(1);
}
printf("Verticesintopologicalorder are :\n");
for(i=1; i<=count; i++)
printf( "%d",topo_order[i]);
printf("\n");
return0;
}/*Endofmain()*/
```

## Output:

![Screenshot 2025-05-06 220016](https://github.com/user-attachments/assets/aef7097c-c441-41fd-8628-890cccf0a1b2)


## Result:
Thus, the C program for determining whether the topological ordering for the following graph is possible or not, is implemented successfully.
