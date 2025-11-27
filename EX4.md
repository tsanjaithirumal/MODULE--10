## Ex.No:4
## Ex.Name: Adjacency List Representation of a Graph
## Date: 27/10/25
## Aim:
To write a C++ program to represent a graph using adjacency list.



<img width="402" height="275" alt="481636721-cddd561f-36fe-4646-bdcf-72b2838e951c" src="https://github.com/user-attachments/assets/fb6d932e-d595-444d-b18d-9ba652862198" />


## Algorithm:
Start the program.

Create an adjacency list using vector<int> adj[].

Read the number of edges in the graph.

For each edge (u, v):

Insert v into adj[u].

Insert u into adj[v] (if the graph is undirected).

Print the adjacency list representation for all vertices.

Stop the program.

## Program:
```
#include<iostream>
#include<list>
#include<iterator>
using namespace std;
void displayAdjList(list<int> adj_list[], int v)
{
   for(int i = 0; i<v; i++)
   {
      cout << i << "--->";
      list<int> :: iterator it;
      for(it = adj_list[i].begin(); it != adj_list[i].end(); ++it)
      {
         cout << *it << " ";
      }
      cout << endl;
   }
}
void add_edge(list<int> adj_list[], int u, int v)
{
   adj_list[u].push_back(v);
   adj_list[v].push_back(u);
}
int main() 
{
   
   int v = 6,a,b;
   list<int> adj_list[v];
   for(int i=0;i<6;i++)
   {
       cin>>a>>b;
       add_edge(adj_list, a, b);
   }
   displayAdjList(adj_list, v);
   return 0;
}
```
## Output:


<img width="864" height="824" alt="481636938-9247161f-2442-425e-8879-5fff8fab796e" src="https://github.com/user-attachments/assets/730a0177-1bbd-4585-b0c6-e59b04f83867" />



## Result:
The Program Executed Successfully.
