# Graphs DS

## Some points and gotchas with GraphsDS and Algo

Degree applies only to Weighted Graphs.

## Disjoint sets for Finding whether 2 vertices are connected

We initialize the Disjoint Sets with Each Vertex.

For Each Edge we encounter we do a Union for the 2 Vertices.

So A Disjoint set will have 3 operations:

* Initialize the set with each vertex so the size of the set becomes numbwer of Vertices of the graph.

* Find operation which will give us  the parent or Connectedness information for a Vertex.

* Union operation which we will do for each Edge we encounter and then change the disjointed-ness for the vertices.

* So the initialization is ran for n Vertices and then Union for each Edge so atleast n-1 times.

## For Connectedness Disjoint Sets can be implemented in a few ways

### Quick Find

 In Quick find we Want to be able to execute the find function in O(1) time. The value of the Root array will directly give us the value of the Root.

 Union operation becomes a bit more tricky, on each union operation between (Vertex X and Vertex Y) we choose say Vertex X as the root and update the root of Vertex Y to be X.

 Then we traverse the array to change all the Vertices which have their parent as Y to X. ( Loop here )

 This makes it is super simple to find connectedness of a Vertex X and Vertex Y as their root element will be the same.

 But the Union opertation means traversing the entire array and replacing vertexes wherever needed.

 So Union becomes a O(n) everytime as we traverse the entire array.

 Find is O(1) constant time.

 Connectedness is also O(1) constant time as we need to just check the set entry.

### Quick Union

 In Quick Union, the Union operation is faster almost constant time O(1).

 The Find operation uses a looping logic.

 Initially all elements of the are initialized as the Vertex, being their own parents.

 Union step is simpler: Union of Vertex X and Vertex Y means if find(X) is not the same as find(Y) then X and Y belong to different parents. So in these cases change Value of Y to the find(X)

 Basically we replace the parents to avoid one level of traversal.

 For the find method we have a loop, basically navigate the structure till we get an element which has the same parent as itself.

 So by traversing the array we reach the top most root.

 All the steps take O(N) time here but in the worst case. In most cases it is less than O(N).

### Union By rank

Optimized version of Quick Union.

The complexity of find for Quick Union is O(h) which is the height of the tree we generate.

So if we can balance the height of the tree slightly then our complexity for find will get better.

Here we make a slight modificaion in our logic. When we do a Union of Vertex X and Vertex Y we make the parent as Vertex with higher rank or height.

This is a greedy implementation which ensure a well spread out tree rather than a linear structure of randomly picking up the parent node