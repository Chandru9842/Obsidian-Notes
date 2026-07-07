

The **Bellman-Ford algorithm** is used to find the **shortest distance from a single source to all other vertices** in a weighted graph.

Unlike Dijkstra's algorithm, Bellman-Ford **works even if the graph has negative edge weights**.

---

## When to Use Bellman-Ford

✅ Graph has negative edge weights.

✅ Need to detect a negative weight cycle.

❌ Not as fast as Dijkstra for graphs with only positive weights.

---

## Time Complexity

- **Time:** O(V×E)O(V \times E)O(V×E)
- **Space:** O(V)O(V)O(V)

where:

- **V** = Number of vertices
- **E** = Number of edges

---

# Main Idea

A shortest path can contain at most **V − 1 edges**.

Therefore, **relax all edges V − 1 times**.

### Relaxation

If

```
dist[u] + wt < dist[v]
```

then update

```
dist[v] = dist[u] + wt
```

---

# Algorithm

1. Initialize every distance as Infinity.
2. Source distance = 0.
3. Repeat **V−1** times:
    - Traverse every edge.
    - Relax the edge.
4. Traverse all edges one more time.
    - If any distance still decreases,  
        → Negative Cycle exists.

---

# Example

Suppose

```
0 ----4----> 1|            |5           -2|            |v            v2 ----3----> 3
```

Source = 0

Edges

```
0 → 1 (4)0 → 2 (5)1 → 3 (-2)2 → 3 (3)
```

Initially

```
dist = [0, INF, INF, INF]
```

---

### First Iteration

Edge

```
0→10+4 < INFdist[1]=4
```

```
dist=[0,4,INF,INF]
```

---

Edge

```
0→20+5<INFdist[2]=5
```

```
dist=[0,4,5,INF]
```

---

Edge

```
1→34+(-2)=2dist[3]=2
```

```
dist=[0,4,5,2]
```

---

Edge

```
2→35+3=88>2No update
```

After first iteration

```
[0,4,5,2]
```

Second and third iterations produce no changes.

Final Answer

```
0 : 01 : 42 : 53 : 2
```

---

# Why V−1 Iterations?

Consider

```
0 → 1 → 2 → 3
```

The shortest path to node 3 uses **3 edges**.

In general,

```
Maximum edges in a shortest path = V−1
```

So we relax all edges **V−1** times.

---

# Negative Cycle Detection

After completing **V−1** iterations, run one more pass over all edges.

If

```
dist[u] + wt < dist[v]
```

is still true,

then a **negative weight cycle** exists.

Example:

```
0 → 1 (1)1 → 2 (-2)2 → 0 (-2)
```

Cycle weight

```
1 + (-2) + (-2)= -3
```

The total weight is negative, so each trip around the cycle reduces the path cost indefinitely. Bellman-Ford detects this because distances keep improving even after V−1 iterations.

---

# Java Implementation

class Pair {
    int first;
    int second;

    Pair(int first, int second) {
        this.first = first;
        this.second = second;
    }
}

class Solution {

    public int[] bellmanFord(int V, int[][] edges, int src) {

        List<ArrayList<Pair>> adj = new ArrayList<>();

        for (int i = 0; i < V; i++)
            adj.add(new ArrayList<>());

        for (int[] e : edges) {
            int u = e[0];
            int v = e[1];
            int w = e[2];

            adj.get(u).add(new Pair(v, w));
        }

        int[] dist = new int[V];
        Arrays.fill(dist, (int)1e9);

        dist[src] = 0;

        // Relax edges V-1 times
        for (int i = 0; i < V - 1; i++) {

            for (int u = 0; u < V; u++) {

                for (Pair it : adj.get(u)) {

                    int adjNode = it.first;
                    int wt = it.second;

                    if (dist[u] != (int)1e9 &&
                        dist[u] + wt < dist[adjNode]) {

                        dist[adjNode] = dist[u] + wt;
                    }
                }
            }
        }

        // Negative cycle check
        for (int u = 0; u < V; u++) {

            for (Pair it : adj.get(u)) {

                int adjNode = it.first;
                int wt = it.second;

                if (dist[u] != (int)1e9 &&
                    dist[u] + wt < dist[adjNode]) {

                    return new int[]{-1};
                }
            }
        }

        return dist;
    }
}

---

# Dijkstra vs Bellman-Ford

|Feature|Dijkstra's algorithm|Bellman-Ford|
|---|---|---|
|Negative weights|❌ No|✅ Yes|
|Detect negative cycle|❌ No|✅ Yes|
|Time Complexity|O((V+E) log V)|O(V × E)|
|Relaxation|Uses priority queue|Relaxes every edge repeatedly|
|Best for|Positive-weight graphs|Graphs with negative weights or when cycle detection is needed|

### Key Interview Points

- Bellman-Ford is a **single-source shortest path** algorithm.
- It **supports negative edge weights**.
- It **detects negative weight cycles**.
- The core idea is **edge relaxation repeated V−1 times**, followed by one extra pass to check for a negative cycle.


Let's understand **negative cycle detection** step by step.

---

# What is a Negative Cycle?

A **negative cycle** is a cycle whose total edge weight is **less than 0**.

Example:

```
      1
0 --------> 1
^           |
|           |
|-2       -2|
|           |
+-----------+
      2
```

Edges:

0 → 1 = 1
1 → 2 = -2
2 → 0 = -2
```

Cycle weight:

```
1 + (-2) + (-2) = -3
```

Since the total is **-3**, every time you travel around the cycle, your distance decreases by 3.

---

# Why is this a problem?

Suppose the source is `0`.

Initially:

```
dist = [0, INF, INF]
```

---

## First Relaxation

### Edge `0 → 1`

```
0 + 1 = 1
```

```
dist = [0, 1, INF]
```

---

### Edge `1 → 2`

```
1 + (-2) = -1
```

```
dist = [0, 1, -1]
```

---

### Edge `2 → 0`

```
-1 + (-2) = -3
```

```
dist = [-3, 1, -1]
```

Notice what happened:

The distance to the **source itself** became **-3**.

---

# Second Relaxation

Now start again.

### Edge `0 → 1`

```
-3 + 1 = -2
```

```
dist = [-3, -2, -1]
```

---

### Edge `1 → 2`

```
-2 + (-2) = -4
```

```
dist = [-3, -2, -4]
```

---

### Edge `2 → 0`

```
-4 + (-2) = -6
```

```
dist = [-6, -2, -4]
```

The distances became even smaller.

---

# Third Relaxation

Again:

```
0 → 1-6 + 1 = -5
```

```
dist = [-6, -5, -4]
```

---

```
1 → 2-5 - 2 = -7
```

```
dist = [-6, -5, -7]
```

---

```
2 → 0-7 - 2 = -9
```

```
dist = [-9, -5, -7]
```

The distances keep decreasing.

---

# Observation

After every round:

```
00↓-3↓-6↓-9↓-12↓...
```

There is **no shortest path**, because you can keep going around the negative cycle and make the path cost smaller forever.

---

# Why does Bellman-Ford run `V - 1` times?

In a graph with `V` vertices, a shortest path can have at most `V - 1` edges.

So after `V - 1` relaxations, **all shortest distances should already be finalized** if there is no negative cycle.

---

# The Extra Check

After the `V - 1` relaxations, Bellman-Ford checks every edge one more time:

```
if (dist[u] != INF &&    dist[u] + wt < dist[v]) {    return new int[]{-1};}
```

### What does this condition mean?

Suppose after all relaxations:

```
dist[2] = -7dist[0] = -9
```

For the edge:

```
2 → 0 (-2)
```

Compute:

```
dist[2] + (-2)= -7 + (-2)= -9
```

If `dist[0]` is already `-9`, then:

```
-9 < -9 ?No
```

No update.

But if it were:

```
dist[0] = -8
```

then:

```
-9 < -8Yes!
```

This means **even after `V - 1` relaxations, we can still reduce a distance**.

That should never happen in a graph without negative cycles.

So Bellman-Ford concludes:

> **A negative weight cycle exists.**

---

# Visual Intuition

### Normal Graph

```
0 → 1 → 2 → 3
```

After `V - 1` relaxations:

```
0 2 5 8
```

One more check:

```
Can any edge reduce a distance?No.
```

Everything is finished.

---

### Graph with Negative Cycle

```
0 → 1↑   ↓└── 2
```

Every time you go around:

```
Distance0↓-3↓-6↓-9↓-12↓...
```

The distances never stop decreasing.

So the **extra pass** detects that an edge can still be relaxed, proving the presence of a negative cycle.

---

## Easy Interview Rule

- **First `V - 1` passes:** Compute the shortest distances by relaxing edges.
- **One extra pass:** If **any** edge can still be relaxed, the graph contains a **negative weight cycle**, so there is no well-defined shortest path for the affected vertices.