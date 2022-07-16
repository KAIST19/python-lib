# NetworkX

## Creating a graph

```python
import networkx as nx
G = nx.Graph()
```

## Nodes

```python
# add a single node
G.add_node(1)

# add multiple nodes
G.add_nodes_from([2, 3])

# add nodes with attributes
G.add_nodes_from([
...     (4, {"color": "red"}),
...     (5, {"color": "green"}),
... ])

# add nodes from another graph
G.add_nodes_from(H)
```

## Edges

```python
# connect 1, 2
G.add_edge(1, 2)

# connect 1, 2 and 3, 4
G.add_edges_from([(1, 2), (1, 3)])

# connect 2, 3
e = (2, 3)
G.add_edge(*e)

# import edges from another graph
G.add_edges_from(H.edges)

# add node "spam"
G.add_node("spam")

# add nodes 's', 'p', 'a', 'm'
G.add_nodes_from("spam")
```

## Counting Nodes and Edges

```python
>>> G.number_of_nodes()
8
>>> G.number_of_edges()
3
```

## Directed Graph
```python
DG = nx.DiGraph()
DG.add_edge(2, 1) # adds the nodes in order 2, 1
DG.add_edge(1, 3)
DG.add_edge(2, 4)
DG.add_edge(1, 2)
```

## Examining elements of a graph
```python
>>> list(G.nodes)
[1, 2, 3, 'spam', 's', 'p', 'a', 'm']

>>> list(G.edges)
[(1, 2), (1, 3), (3, 'm')]

# or list(G.neighbors(1))
>>> list(G.adj[1])
[2, 3]

# the number of edges incident to 1
>>> G.degree[1]
2
```

## Examining elements of a graph
```python
>>> G.remove_node(2)
>>> G.remove_nodes_from("spam")
>>> G.remove_edge(1, 3)
```