# mst
Sollin's/Boruvka’s algorithm for finding minimum weight spanning tree

There are three main algorithms used for computing minimum weight spanning algorithms. We give a brief description of each, and we implement and analyze Sollin’s algorithm.

## Prims:

• Data structures used: min heap

• The idea is to start with an arbitrary vertex v and add its (outgoing) edges to a min heap. Then remove the min edge (v,u) and add mark the node u as part of the MST, add all of u’s outgoing edges that go to nodes not yet marked as part of the MST to the min heap.

• Prims: https://www.youtube.com/watch?v=Uj47dxYPow8

• 𝑂𝑂(𝑛𝑛𝑛𝑛log𝑑𝑑𝑛𝑛+𝑚𝑚log𝑑𝑑𝑚𝑚) when using d-heaps

## Kruskal’s:

• Data structures used: disjoint set, min heap

• The idea is to let each vertex be a disjoint set and place all the edges in a min heap. Remove the minimum edge from the heap, if it connects to disjoint sets, union those sets and add the edge to the MST, if the edge does not connect to disjoint sets discard the edge. Continue until only one set left.

• Kruskal’s: https://www.youtube.com/watch?v=Yo7sddEVONg

• Running time: O(m log n)

## Sollin’s/Boruvka’s:

• Data structures used: disjoint set, min heaps

• Kind of a cross between Prims and Kruskals.

• First let each vertex be a disjoint set. The to each disjoint set create a min heap of edges leaving that tree. Loop through the disjoint sets (trees) and choose the min edge from its min heap, take the new reached vertex and union its set with the present one and merge their corresponding min heaps. Continue looping through the disjoint sets until there is only one set.

• Sollin’s algorithm: https://www.youtube.com/watch?v=t92xyTDvl_c

• Running time: O(m log n)


## Performance Comparison: 

Kruskl’s generally performs worse than either of the other two. As graphs grow large, Prims performs better on dense graphs than Sollins, and Sollins performs better than Prims on sparse graphs.
