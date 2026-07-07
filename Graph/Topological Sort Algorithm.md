
## Topological Sort Algorithm

**Topological Sort** is a linear ordering of the vertices of a **Directed Acyclic Graph (DAG)** such that for every directed edge **u → v**, vertex **u** appears before **v** in the ordering.

> **Works only for Directed Acyclic Graphs (DAGs).**

### Example

```
    5 → 2 → 3    ↓    ↓    0    1
```

One valid topological ordering is:

```
5 0 2 3 1
```

Another valid ordering:

```
5 2 0 3 1
```

There can be multiple valid topological orders.

---

# Algorithm 1: DFS (Stack Method)

### Idea

- Visit a node.
- Recursively visit all its neighbors.
- After visiting all neighbors, push the node into a stack.
- Finally, pop all elements from the stack.

### Steps

1. Create a visited array.
2. Run DFS for every unvisited node.
3. Push the node into the stack after visiting all neighbors.
4. Pop the stack to get the topological order.

---

### Java Code

class Solution {

    public void dfs(int node, ArrayList<ArrayList<Integer>> adj,
                    boolean[] vis, Stack<Integer> st) {

        vis[node] = true;

        for (int it : adj.get(node)) {
            if (!vis[it]) {
                dfs(it, adj, vis, st);
            }
        }

        st.push(node);
    }

    public int[] topoSort(int V, ArrayList<ArrayList<Integer>> adj) {

        boolean[] vis = new boolean[V];
        Stack<Integer> st = new Stack<>();

        for (int i = 0; i < V; i++) {
            if (!vis[i]) {
                dfs(i, adj, vis, st);
            }
        }

        int[] ans = new int[V];
        int index = 0;

        while (!st.isEmpty()) {
            ans[index++] = st.pop();
        }

        return ans;
    }
}

---

### Time Complexity

- DFS = **O(V + E)**

### Space Complexity

- Visited = **O(V)**
- Stack = **O(V)**
- Recursion Stack = **O(V)**

Total: **O(V)**

---

# Algorithm 2: Kahn's Algorithm (BFS)

### Idea

A node can appear first only if its **indegree = 0**.

### Steps

1. Find the indegree of every node.
2. Put all nodes with indegree 0 into a queue.
3. Remove a node from the queue.
4. Add it to the answer.
5. Reduce the indegree of its neighbors.
6. If any neighbor's indegree becomes 0, push it into the queue.
7. Repeat until the queue becomes empty.

---

### Example

Graph:

```
0 → 1↓2 → 3
```

Indegree:

```
0 : 01 : 12 : 13 : 1
```

Queue:

```
0
```

Process:

```
Remove 0Answer:0Decrease indegree:1 becomes 02 becomes 0Queue:1 2Remove 1Answer:0 1Remove 2Decrease indegree of 3Queue:3Remove 3Answer:0 1 2 3
```

---

### Java Code

```
class Solution {

    public int[] topoSort(int V, ArrayList<ArrayList<Integer>> adj) {

        int[] indegree = new int[V];

        // Calculate indegree
        for (int i = 0; i < V; i++) {
            for (int it : adj.get(i)) {
                indegree[it]++;
            }
        }

        Queue<Integer> q = new LinkedList<>();

        // Add all nodes with indegree 0
        for (int i = 0; i < V; i++) {
            if (indegree[i] == 0) {
                q.offer(i);
            }
        }

        int[] ans = new int[V];
        int index = 0;

        while (!q.isEmpty()) {

            int node = q.poll();
            ans[index++] = node;

            for (int it : adj.get(node)) {

                indegree[it]--;

                if (indegree[it] == 0) {
                    q.offer(it);
                }
            }
        }

        return ans;
    }
}```

---

### Time Complexity

- Finding indegree = **O(E)**
- BFS = **O(V + E)**

Overall:

**O(V + E)**

Space:

- Queue = **O(V)**
- Indegree = **O(V)**

---

# DFS vs Kahn's Algorithm

|Feature|DFS|Kahn (BFS)|
|---|---|---|
|Technique|DFS + Stack|BFS + Queue|
|Uses Indegree|❌ No|✅ Yes|
|Detect Cycle|Not directly|✅ Yes|
|Time|O(V + E)|O(V + E)|
|Space|O(V)|O(V)|

---

## Cycle Detection with Kahn's Algorithm

A topological ordering is possible **only if the graph has no cycles**.

After running Kahn's algorithm:

```
if (index != V) {    System.out.println("Cycle exists");} else {    System.out.println("No cycle");}
```

If the number of processed nodes (`index`) is less than `V`, some nodes could not be processed because they are part of a cycle.

---

## Common Interview Problems

- Course Schedule
- Course Schedule II
- Alien Dictionary
- Eventual Safe States
- Find Eventual Safe Nodes
- Parallel Courses
- Detect Cycle in a Directed Graph (using Kahn's Algorithm)

### Quick Tip

- **Need only topological order?** Use either **DFS** or **Kahn's Algorithm**.
- **Need to detect a cycle in a directed graph?** **Kahn's Algorithm** is often the easiest choice because if the number of processed nodes is less than `V`, a cycle exists.