## Ex.No:3
## Ex.Name: Topological Sorting using List and Stack
## Date: 27/10/25
## Aim:
To write a C++ program to perform Topological Sorting for a Directed Acyclic Graph (DAG) using adjacency list and stack.

## Algorithm:
Start the program.

Represent the graph using adjacency lists (vector<int> adj[]).

Create a visited[] array to mark visited nodes.

Implement a recursive function topoSortUtil(v):
Mark the current node as visited.
Recursively call topoSortUtil() for all adjacent vertices.
Push the current node into the stack after visiting all its neighbors.

In main(), for all unvisited nodes, call topoSortUtil().

Pop elements from the stack to get the Topological Ordering.

Print the ordering.

Stop the program.

## Program:
```
#include <iostream>
#include <list>
#include <stack>
using namespace std;

class Graph {
	int V; 

	list<int>* adj;

	void topologicalSortUtil(int v, bool visited[], stack<int>& Stack);

public:
	Graph(int V); 

	void addEdge(int v, int w);

	void topologicalSort();
};

Graph::Graph(int V)
{
	this->V = V;
	adj = new list<int>[V];
}

void Graph::addEdge(int v, int w)
{
	adj[v].push_back(w); 
}

void Graph::topologicalSortUtil(int v, bool visited[],
								stack<int>& Stack)
{
	
	visited[v] = true;

	list<int>::iterator i;
	for (i = adj[v].begin(); i != adj[v].end(); ++i)
		if (!visited[*i])
			topologicalSortUtil(*i, visited, Stack);

	Stack.push(v);
}

void Graph::topologicalSort()
{
	
	stack <int> Stack;
	bool* visited = new bool [V];
	for(int i=0; i<V; i++)
	{
	    visited[i]=false;
	}
	for(int i=0; i<V; i++)
	{
	    if(visited[i]==false)
	    {
	        topologicalSortUtil (i, visited, Stack);
	    }
	}
	while(Stack.empty()==false)
	{
	    cout<<Stack.top()<<" ";
	    Stack.pop();
	}
}

int main()
{
    int a,b,n;
    cin>>n;
    Graph g(n);
    for(int i=0; i<6; i++)
    {
        cin>>a>>b;
        g.addEdge(a,b);
    }
    cout<<"Topological Sort of the given graph n"<<endl;
    g.topologicalSort();
	return 0;
}
```
## Output:

<img width="873" height="732" alt="image" src="https://github.com/user-attachments/assets/623edefa-e999-4792-b0dd-19dda2730171" />

## Result:
The Program Executed Successfully.
