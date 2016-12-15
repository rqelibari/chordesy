# Chordesy
A little python module to find chordless cycles in planar maps.

# Idea
In a graph visualization (e.g. a street map) enclosed space (e.g a place where
buildings would be built) may be important. This python module finds those
enclosed spaces.

# How does it work?
The module builds on a [undirected planar 2d graph][1], which is an ordered
pair (V,E), where V is a set of R^2-points, called vertecies, and E is a set of
two-element subsets of V, called edges.

With this datastructure the solution is as simple as using a DFS circle
algorithm with the additional condition, that on each vertex v, which is not
the starting vertex s, the nearest edge n on the right side (in R^2 space) of
the edge e, leading to that vertex v is taken next. In other words:
There is no other edge in the angle between n and e.
This corresponds to a car turing right at every junction.

[1]: https://en.wikipedia.org/wiki/Graph_(discrete_mathematics)