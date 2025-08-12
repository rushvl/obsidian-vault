
## Terminology

### Networks
A network is a directed [[Graph]] G with vertex set V and edges E combined with a function C which maps all edges to some non-negative integer(or real number) which is called the capacity of edge e.

### Flow Network
Additionally in the network if we label 2 nodes as source and sink this is called a flow network.
Source(s) = No In edges
Sink(t) = No Out edges

### Flow
A function F which maps all edges to some non negative integer which is called the flow through edge e.
This function has to fulfill 2 conditions.
1. Flow of edge <= capacity of edge
2. For all vertices except sink or sink, the inflow should be equal to out flow

### Maximum Flow
This is the flow of maximum possible value from source to sink.

### Residual Capacity
Residual Capacity of an edge is defined as capacity-flow.

### Reverse Edge Residual Capacity
Capacity of reverse edge - flow in reverse edge

If Flow of edge (u , v) = x
Then Flow of edge(v , u) = -x

Capacity of reverse edge = 0 ( edge is imaginary )



## Algorithms

1.  [[Ford Fulkerson]]