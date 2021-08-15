# Graphs DS

## Some points and gotchas with GraphsDS and Algo

Degree applies only to Weighted Graphs.

### Disjoint sets for Finding whether 2 vertices are connected

We initialize the Disjoint Sets with Each Vertex.

For Each Edge we encounter we do a Union for the 2 Vertices.

So A Disjoint set will have 3 operations:

* Initialize the set with each vertex so the size of the set becomes numbwer of Vertices of the graph.

* Find operation which will give us  the parent or Connectedness information for a Vertex.

* Union operation which we will do for each Edge we encounter and then change the disjointed-ness for the vertices.

* So the initialization is ran for n Vertices and then Union for each Edge so atleast n-1 times.

### For Connectedness Disjoint Sets can be implemented in a few ways

#### Quick Find

 In Quick find we update the value of each Vertex to be the absolute Root of the subtree found till that point.

 This means the Find operartion becomes O(n) linear operation.

 Union operation becomes a bit more tricky as we want to find the root of each subtree recursively till we reach the topmost parent.

 
