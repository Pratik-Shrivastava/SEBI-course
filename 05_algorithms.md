# 🌳 Data Structures & Algorithms – Traversals, Graphs, and Core Concepts

---

## 1. TREE AND GRAPH TRAVERSALS

### 1.1 TREE TRAVERSALS

**Concept:**  
Traversal = systematically visiting every node of a tree exactly once.  
Used in evaluating expressions, file systems, or hierarchical structures.

**Mini Diagram:**
```
        A
       / \
      B   C
     / \
    D   E
```

**Traversal Types:**

| Type | Order | Example Output |
|------|--------|----------------|
| Preorder | Root → Left → Right | A B D E C |
| Inorder | Left → Root → Right | D B E A C |
| Postorder | Left → Right → Root | D E B C A |
| Level Order | Top to bottom (BFS) | A B C D E |

**Recursive Pseudocode:**
```text
INORDER(node):
  if node != NULL:
      INORDER(node.left)
      print(node.data)
      INORDER(node.right)
```

**Explanation:** Recursive calls push left children first (depth-first), process root, then right child.  
**Complexity:** Time = O(n) | Space = O(h) where h = height of tree

**Practice:**
- Write a recursive preorder traversal.
- Perform level-order traversal using a queue.

**MCQs:**
- Inorder traversal of BST yields → ✅ Sorted output  
- Preorder useful for → ✅ Copying tree structure  
- Level order uses → ✅ Queue  

---

### 1.2 GRAPH TRAVERSALS

**Concept:** Traversing all vertices and edges of a graph using systematic search methods.

**Graph Example:**
```
A — B — C
|    \
D     E
```

**Depth First Search (DFS)**
```text
DFS(node):
  mark node visited
  for each neighbor of node:
     if not visited:
         DFS(neighbor)
```
Flow: Start at A → go as deep as possible → backtrack.  
**Order:** A, B, C, E, D

**Breadth First Search (BFS)**
```text
BFS(start):
  enqueue(start)
  mark visited
  while queue not empty:
      v = dequeue()
      for each unvisited neighbor of v:
          enqueue(neighbor)
```
Flow: Visit neighbors level by level.  
**Order:** A, B, D, C, E  
**Complexity:** O(V + E)

**MCQs:**
- DFS uses → ✅ Stack (or recursion)  
- BFS uses → ✅ Queue  
- Traversal complexity → ✅ O(V+E)  

---

## 2. CONNECTED COMPONENTS

**Concept:**  
In an undirected graph, a connected component is a subgraph in which every pair of nodes is connected.

**Example Graph:**
```
Component 1: A—B—C
Component 2: D—E
```

**Algorithm:**
```text
count = 0
for each vertex v:
  if not visited:
     DFS(v)
     count++
```
**Explanation:** Each DFS/BFS from an unvisited node explores one component.  
**Output:** Number of connected components = 2  
**Complexity:** O(V + E)

**MCQs:**
- A connected graph has → ✅ 1 component  
- Algorithm used → ✅ DFS or BFS  
- Used to find → ✅ Isolated subgraphs  

---

## 3. SPANNING TREES

**Concept:**  
A Spanning Tree connects all vertices with minimum edges and no cycles.  
A Minimum Spanning Tree (MST) minimizes total edge weights.

**Mini Diagram:**
```
Graph: A—B(2), A—C(3), B—C(1)
MST: edges (B—C, A—B) → Total = 3
```

**Kruskal’s Algorithm (Greedy)**
```text
Sort edges by weight
for each edge (u,v):
  if u,v not in same set:
     include edge
     union(u,v)
```
**Flow:**
1. Sort edges  
2. Add smallest edge without cycle  
3. Repeat until V-1 edges added

**Prim’s Algorithm (Greedy)**
```text
Initialize key[v]=∞
key[start]=0
while unvisited:
   pick vertex u with min key
   for each v adjacent to u:
       if weight(u,v) < key[v]:
           key[v] = weight(u,v)
```
Start at vertex A → pick smallest adjacent edge → expand tree gradually.  
**Complexity:** O(E log V)

**MCQs:**
- MST edges = ✅ V−1  
- Kruskal’s uses → ✅ Union-Find  
- Prim’s grows → ✅ Vertex by vertex  

---

## 4. SHORTEST PATH ALGORITHMS

**Concept:** Find minimum path cost between nodes in a weighted graph.

| Algorithm | Type | Works with | Technique |
|------------|------|-------------|------------|
| Dijkstra’s | Single Source | Non-negative edges | Greedy |
| Bellman-Ford | Single Source | Negative edges | DP |
| Floyd-Warshall | All Pairs | Any weights | DP |

### Dijkstra’s Algorithm
```text
dist[source] = 0
while nodes remain:
  u = min distance unvisited node
  for each neighbor v:
     if dist[v] > dist[u] + w(u,v):
        dist[v] = dist[u] + w(u,v)
```
**Mini Diagram:**
```
A --5-- B
|      / \
2    1   3
|  /      \
C----------D
```
**Shortest A→D = 5 (A→B→D)**  
**Complexity:** O(E log V) with priority queue

### Bellman-Ford Algorithm
```text
for i=1 to V-1:
  for each edge (u,v):
     if dist[v] > dist[u] + w(u,v):
         dist[v] = dist[u] + w(u,v)
```
Detects negative cycles if still updated in Vth iteration.  
**Complexity:** O(V·E)

### Floyd-Warshall Algorithm
```text
for k=1 to V:
 for i=1 to V:
  for j=1 to V:
     dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j])
```
**Complexity:** O(V³)

**MCQs:**
- Dijkstra fails for → ✅ Negative weights  
- Bellman-Ford detects → ✅ Negative cycles  
- Floyd-Warshall computes → ✅ All-pairs shortest paths  

---

## 5. HASHING

**Concept:** A hashing algorithm maps keys to indices in a hash table for fast lookup.

**Mini Diagram:**
```
Key → Hash Function → Index
(Example: key % 10)
```

**Collision Handling Methods:**

| Method | Description | Example |
|---------|--------------|----------|
| Chaining | Linked list at each index | 12→22→32 |
| Linear Probing | Next empty slot | (i+1)%size |
| Quadratic Probing | Skip by i² | (i+i²)%size |
| Double Hashing | Use secondary hash | (h1 + i*h2) |

**Complexity:** Average O(1), Worst O(n)

**MCQs:**
- Hashing reduces search time from O(n) → ✅ O(1)  
- Collision handling via → ✅ Chaining  
- Good hash minimizes → ✅ Clustering  

---

## 6. SORTING

**Concept:** Arrange data in ascending/descending order for efficient searching and analysis.

| Algorithm | Type | Time (Avg) | Space | Stable |
|------------|------|-------------|--------|---------|
| Bubble | Simple | O(n²) | O(1) | ✅ |
| Selection | Simple | O(n²) | O(1) | ❌ |
| Insertion | Simple | O(n²) | O(1) | ✅ |
| Merge | Divide & Conquer | O(n log n) | O(n) | ✅ |
| Quick | Divide & Conquer | O(n log n) | O(log n) | ❌ |
| Heap | Tree-based | O(n log n) | O(1) | ❌ |

**Mini Diagram (Quick Sort):**
```
Pivot = 5
Partition: [3,2] 5 [8]
Recurse → [2,3,5,8]
```

**MCQs:**
- Merge sort space → ✅ O(n)  
- Quick sort worst case → ✅ O(n²)  
- Heap sort uses → ✅ Binary heap  

---

## 7. SEARCHING

**Concept:** Find an item in a dataset.

| Algorithm | Requirement | Time |
|------------|--------------|------|
| Linear Search | None | O(n) |
| Binary Search | Sorted array | O(log n) |

**Binary Search Pseudocode:**
```text
low=0, high=n-1
while low<=high:
   mid=(low+high)/2
   if arr[mid]==key → return mid
   else if key<arr[mid] → high=mid-1
   else low=mid+1
```

**Mini Diagram:**
```
Array: [10,20,30,40,50], key=30
mid=2 → Found
```

**MCQs:**
- Binary search only works on → ✅ Sorted data  
- Recursive depth = → ✅ log₂n  
- Linear search best case → ✅ O(1)  

---

## 8. DESIGN TECHNIQUES

### 8.1 GREEDY METHOD

**Concept:** At each step, choose locally best solution hoping for global optimum.

**Example Problems:** Fractional Knapsack, Prim’s & Kruskal’s MST, Dijkstra’s shortest path.

**Mini Flow (Kruskal):**
1. Sort edges  
2. Pick smallest edge without cycle  
3. Repeat till V-1 edges

**MCQs:**
- Greedy ensures → ✅ Local optimal step  
- Used in → ✅ Dijkstra / Kruskal  

---

### 8.2 DYNAMIC PROGRAMMING (DP)

**Concept:** Solve complex problems by combining results of overlapping subproblems.

**Example:** Fibonacci, 0/1 Knapsack, Bellman-Ford.

**Mini Diagram:**
```
fib(5)
↙      ↘
fib(4) fib(3)
↙↘    ↙↘
```

**Memoization Example:**
```text
if n<=1 return n
if dp[n] != -1 return dp[n]
dp[n]=fib(n-1)+fib(n-2)
```
**Complexity:** O(n)

**MCQs:**
- DP uses → ✅ Overlapping subproblems  
- Stores → ✅ Sub-results  

---

### 8.3 DIVIDE AND CONQUER

**Concept:** Divide problem → Solve subproblems → Combine results.

**Examples:** Merge sort, Quick sort, Binary search.

**Mini Flow (Merge Sort):**
1. Divide → [Left][Right]  
2. Sort each half  
3. Merge results

**MCQs:**
- Binary search uses → ✅ Divide & Conquer  
- Merge sort time → ✅ O(n log n)  

---

## ✅ FINAL REVISION TABLE

| Concept | Algorithm | Time Complexity |
|----------|------------|-----------------|
| Traversals | DFS/BFS | O(V+E) |
| Connected Components | DFS | O(V+E) |
| Spanning Trees | Kruskal / Prim | O(E log V) |
| Shortest Path | Dijkstra / Bellman-Ford | O(E log V) / O(VE) |
| Hashing | h(k)=k%size | O(1) avg |
| Sorting | Merge / Quick | O(n log n) |
| Searching | Binary Search | O(log n) |
| Design | Greedy, DP, D&C | Depends on case |

