# DSA

### Definations


 <details>
 <summary>Answer</summary>
  
     Algorithms: These are the methods of solving problems.
     Data Structures: Store the information associated with the problem.
  
     Data Types: Stack,Queue,Bag, Union-find, priority queue
     Sorting: Quicksort,Mergesort,Heapsort,Radixsorts
     Searching: BST,red-black BST, hash table
     Graphs: BFS,DFS,Prim,Kruskal,Dijkstra
     Strings: KMP,regular expression,TST, Huffman,LZW
     advanced: B-tree,suffix array,maxflow
     
 </details>
  
### Why Study Algorithms?


  <details>
  <summary>Answer</summary>
  
  
   - Their impact is broad and far-reaching.
   - Old roots and new opportunities.
      - Study of algorithms dates at least to Euclid.
      - Formalized by Church and Turing in 1930s.
   - To solve problems that could not otherwise be addressed.
      - Eg. Network Connectivity.
   - For intellectual stimulations.
      - ***Francis Sullivan- For me great algorithms are the poetry of computation. Just like verse, they can be terse,allusive,dense and even mysterious. But once
        unlocked, they cast a rilliant new light on some aspect of computing.***
        
  </details>
  
### Union-Find Problem

  <details>
  <summary>Answer</summary>
   
   - Dynamic Connectivity
   - Quick find
   - Quick union
   - Improvements
   - Applications
 
  </details>
  
  <details>
  <summary>Steps to developing a usable algorithm</summary>
  
   - Model the problem.
   - Find an algorithm to solve it.
   - Fast enough? Fits in memory?
   - If not, figure out why.
   - Find a way to address the problem.
   - Iterate until satisfied.
   
  </details>
  
  <details>
  <summary>Dynamic connectivity</summary>
  
   - **Union command:** connect two objects.
   - **Find/connected query:** is there a path connecting the two objects?
   
   ***Modelling the objects***
   - Pixels in a digital photo.
   - Computers in a network.
   - Friends in a social network.
   - Transistors in a computer chip.
   - Elements in a mathematical set.
   - Variable name in Fortran program.
   - Metallic sites in a composite system.
   
   ***Moddeling the connections***
   We assume "is connected to" is an equivalence relation:
   - Reflexive: p is connected to p.
   - Symmetric: if p is connected to q, then q is connected to p.
   - Transitive: if p is connected to q and q is connected to r, then p is connected to r.
   
   ***Implementing the operations***
   - Find Query: Check if two objects are in the same component.
   - Union Command: Replace components containing two objects with their union.
   
  </details>
       
  
     
