## Ex.No:1
## Ex.Name: Graph Implementation using STL (DFS of Unweighted and Undirected Graph)
## Date: 27/10/25

## Aim:
To write a C++ program to implement a Graph using STL for competitive programming and perform Depth First Search (DFS) on an unweighted and undirected graph.

## Algorithm:
Start the program.

Read the number of edges in the graph.

Create an adjacency list representation of the graph using vector<int> adj[].

For each edge (u, v):

Add v to adj[u].

Add u to adj[v] (since the graph is undirected).

Implement a DFS function:

Mark the starting node as visited.

Recursively visit all its unvisited adjacent vertices.

Call the DFS function from the given starting vertex.

Print the DFS traversal order.

Stop the program.

## Program:
```
#include <bits/stdc++.h>
using namespace std;

void addEdge(vector<int> adj[], int u, int v)
{
    adj[u].push_back(v); //singly linked ,not bidirectional
}

void DFS(vector<int> adj[], int v, vector<bool> &vis)
{
    vis[v] = true;
    cout << v << " ";
    //for(int i=0;i<adj[v].size() ; i++)
    for (auto i : adj[v])
    {
        //if(!vis[adj[v][i]])
        if (vis[i] == false)
            DFS(adj, i, vis);
    }
}

int main()
{ 
    int n,a,b;
    cin>>n;
    vector<int> adj[n];
    vector<bool> visited(n, false);
    for(int i=0; i<n; i++)
    {
        cin>>a>>b;
        addEdge(adj, a,b);
    }
    DFS(adj, 1, visited);
}
```
## Output:
.<img width="863" height="871" alt="481635357-75bb7076-0e4d-427a-96d2-075ed8fe4ab7" src="https://github.com/user-attachments/assets/b17a78a1-fdd6-4ffe-aed7-2af425f4d8a6" />



## Result:
The Program Executed Successfully
