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
   
   - Read in number of objects N from standard input.
   - Repeat:
     - read in pair of integers from standard input 
     - if they are not connected,connect them and print out pair
     
  ```
    
    public static void main(Strings[] args)
    {
       int N = StdIn.readInt();
       UF uf = new UF(N);
       while(!StdIn.isEmpty())
       {
          int p = StdIn.readInt();
          int q = StdIn.readInt();
          if(!uf.connected(p,q))
          {
             uf.union(p,q);
             StdOut.println(p+" "+q);
          }
        }  
      }
      
  ```
    
  </details>
  
### Quick Find
  
  <details>
  <summary>Quick Find</summary>
  Basically called as Eager Approch. 
  - Integer array id[] of size N.
  - Interpretation: p and q are connected iff they have the same id.
          
          
     id[]:
     ---------------------
     |0|1|2|3|4|5|6|7|8|9|
     ---------------------
     
   - Find. Check if p and q have the same id.
      id[6]=0; id[1]=1;
      6 and 1 are not connected
      
   - Union. To merge compnents containing p and q, change all entries whose id equals id[p] to id[q].
   
   </details>
   
### Binary Search Tree

  <details>
  <summary>BST</summary>
  T.C= 0(h)
  where h=height of the tree
  T.C AVG=logn
  
  - What is BST?
    - Left Subtree Nodes<Root
    - Right SubtreeNodes>Root
    - Left and Right Subtrees are also BST with no duplicates.
  
  - Special Property
    -Inorder(left,root,right) Traversal of BST gives a sorted sequence.
  
  - Suppose we are given a key. To find the value we will compare the key with root, if the key is smaller than the rrot then we will traverse in the left else in the right. And do this recursively. T.C=O(h)/logn.
  
  - Skewed trees
    - The trees that are not balance and go in any one direction and follow a linear fashion.
    
  - BST insertion
  
 ```
 
  public class BST{
      static class Node{
          int data;
          Node left;
          Node right;
          Node(int data){
          this.dataa=data;
          }
       }
       //insertion of node in bst
       public static Node insert(Node root,int val){
          if(root==null){
          root=new Node(val);
          return root;
          }
          if(root.data>val){
          root.left=insert(root.left,val);
          }
          else{
          root.right=insert(root.right,val);
          }
          return root;
       }
       public static void inorder(Node root){
       if(root==null){
       return;
       }
       inorder(root.left);
       System.out.print(root.data+"");
       inorder(root.right);
       }
       public static boolean serach(Node root, int key){
       if(root==null){
       return false;
       }
       if(root.data>key){
          return search(root.left,key);    
       }
       else if(root.data==key){
           return true;
           }
       else{
          return search(root.right,key);
       }
       }
       
       public static Node delete(Node root,int val){
       if(root.data>val{
       root.left=delete(root.left,val);
       }
       else if(root.data<val){
       root.right=delete(root.right,val);
       }
       else{ //root.data==val
       //case 1
       if(root.left==null && root.right==null){
       return null;
       }
       //case 2
       if(root.left==null){
       return root.right;
       }
       }
       }
       
       public ststic void main(String args[]){
          int values[]={5,1,3,4,2,7};
          Node root=null;
          for(int i=0;i<values.length;i++){
          root=insert(root,values[i]);
       }
       inorder(root);
       System.out.println();
       if(search(root,1)){//key=1
       System.out.println("found");
       }
       else{
       System.out.println("not found");
       }
    }   
  }
  
```

  - Delete a Node
    - Cases:
      - No child(Leaf Node):Delete Node and Return null to parent.
      - One child:Delete Node and replace with child node.
      - Two Children:Replace value with inorder successor, Delete the node for inorder successor(inorder successor always has 0 or 1 child).
      Inorder successor in BST(by default) is left most in Right subtree.
      
      
  
 </details>

 <details>
 <summary>Trie</summary>
 
 - What is Trie?
   - Prefix
   - Digit Search
   - Retrieval tree
  
  T.C=O(L) 
  
 - Why Trie?
   - Search Fast
   - Root is an empty node.
   - Prefix is not repeated.
   -  
     
       
  </details>
  
  # Graphs
  <details>
  <summary>Graphs</summary>
  
  - Network of points.
  - Network is formed with connections.
  - Nodes in graph are called vertex orvertices.
  - Connections are called edges.
  
  ## Applications of Graphs
  - Maps
  - Social Network
  - Delivery Network9Shortest Cyclic Path)
  
  
  
  - Types of Edges
    - Direction
      - Unidirectional
      - Bidirectional
      - Directed Graph
      - Undirected Graph
    - Weight
      - Weighted
      - Un-weighted
      
  - Storing a Graph
    - Adjacency List
      - Lists of lists
      - 
    - Adjacency Matrix
    - Edge List
    - 2D matrix(Implict Graph)
    
    
