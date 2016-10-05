# grenier

A collection of various algorithms in OCaml.

Licensed under ISC license.

## baltree : Generic balanced-tree
  
A binary tree with smart constructors that ensure the resulting tree is
balanced.

This data structure can be used as a primitive on top of which one can easily
build balanced data structures, including but not limited to binary search
trees.

For instance, implementing stdlib-like Set/Map is trivial and suffers only a ~5
% overhead (and one gains a O(1) length/cardinal operation).

## trope : Track objects accross rope-like operations

This data structure allows efficient implementation of text markers for text editors (see 
[Emacs Markers](http://www.gnu.org/software/emacs/manual/html_node/elisp/Markers.html)).

More generally it allows to track the movement of objects on a line where
chunks are added and removed, with queries O(log n) amortized time.

Finally, it is persistent so you easily compare markers movement between
different revisions. 

## orderme : Order-maintenance problem

See [Order-maintenance problem](https://en.wikipedia.org/wiki/Order-maintenance_problem)
for a detailed description of what this intent to solve.

Main algorithm follows the amortized solution from "Two Simplified
Algorithms for Maintaining Order in a List", Michael A. Bender, Richard Cole,
Erik D. Demaine, Martín Farach-Colton, and Jack Zito..

A managed implementation provide finer integration with OCaml GC to collect
items that are no longer reachable via the public API.

## binpacking : Maxrects rectangle packing implementation

An implementation of Maxrects packing algorithm in 2D.  This algorithm try to
pack a maximum number of 2d boxes inside a 2d rectangle. 

See [Even More Rectangle Bin Packing](http://clb.demon.fi/projects/even-more-rectangle-bin-packing)

Useful for generating spritesheets, texture atlases, etc.

## doubledouble : Floating points with around 107-bits precision 

An implementation of [double-double arithmetic](https://en.wikipedia.org/wiki/Quadruple-precision_floating-point_format#Double-double_arithmetic).

Code is translated from [DD](http://tsusiatsoftware.net/dd/main.html) by Martin Davis.
See [tsusiatsoftware](http://tsusiatsoftware.net) for more information.

## hll : HyperLogLog

An implementation of the HyperLogLog probabilistic cardinality estimator.
See [HyperLogLog](https://en.wikipedia.org/wiki/HyperLogLog).

## jmphash : Jump consistent hashing

An implementation of 
["A Fast, Minimal Memory, Consistent Hash Algorithm"](http://arxiv.org/abs/1406.2294)
from John Lamping and Eric Veach.

## physh : Physical hashtable

Hashtables indexing OCaml values by their physical indentities.  A
proof-of-concept, playing with the GC in tricky ways.

Its main purpose is to efficiently observe sharing, detect cycles, etc, in
arbitrary OCaml values without having to stop and stay out of the OCaml
runtime.

Can be used to experiment and learn about the GC but do expect bugs and don't
expect any kind of compatibility with future OCaml versions.
(Would be nice to have proper upstream support for such feature though!)

## pcg : PCG random generator

Playing with [PCG generators](http://www.pcg-random.org/) in OCaml.
Not even alpha, consider this doesn't exist.
