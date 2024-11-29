Sure! Here's a more concise version with just the essentials, including code in PHP and JavaScript for key algorithms and data structures.

---

### **Basic Data Structures**

1. **Array**: Ordered collection of elements, accessed by index.
   - **Time Complexity**: Access - O(1), Insert/Delete - O(n).

2. **Linked List**:
   - **Singly Linked List**: Nodes contain data and a reference to the next node.
   - **Time Complexity**: Insert/Remove - O(1), Search - O(n).

3. **Stack**: LIFO structure (Last In, First Out).
   - **Push/Pop**: O(1)

   **JavaScript**:
   ```javascript
   let stack = [];
   stack.push(1); // Push
   stack.pop();  // Pop
   ```

   **PHP**:
   ```php
   $stack = [];
   array_push($stack, 1);  // Push
   array_pop($stack);     // Pop
   ```

4. **Queue**: FIFO structure (First In, First Out).
   - **Enqueue/Dequeue**: O(1)

   **JavaScript**:
   ```javascript
   let queue = [];
   queue.push(1); // Enqueue
   queue.shift(); // Dequeue
   ```

   **PHP**:
   ```php
   $queue = [];
   array_push($queue, 1);  // Enqueue
   array_shift($queue);    // Dequeue
   ```

---

### **Advanced Data Structures**

5. **Hash Table**:
   - **Time Complexity**: Search/Insert/Delete - O(1) average.
   
   **JavaScript**:
   ```javascript
   let hashTable = {};
   hashTable['key'] = 'value';  // Insert
   console.log(hashTable['key']); // Search
   delete hashTable['key'];  // Delete
   ```

   **PHP**:
   ```php
   $hashTable = [];
   $hashTable['key'] = 'value';  // Insert
   echo $hashTable['key'];  // Search
   unset($hashTable['key']);  // Delete
   ```

6. **Binary Search Tree (BST)**:
   - **Time Complexity**: Search/Insert/Delete - O(log n) on average.

7. **Trie**: Used for storing strings (efficient prefix searches).

---

### **Algorithms**

8. **Binary Search**:
   - **Time Complexity**: O(log n)

   **JavaScript**:
   ```javascript
   function binarySearch(arr, target) {
       let low = 0, high = arr.length - 1;
       while (low <= high) {
           let mid = Math.floor((low + high) / 2);
           if (arr[mid] === target) return mid;
           else if (arr[mid] < target) low = mid + 1;
           else high = mid - 1;
       }
       return -1;
   }
   ```

9. **Bubble Sort**:
   - **Time Complexity**: O(n²)

   **JavaScript**:
   ```javascript
   function bubbleSort(arr) {
       for (let i = 0; i < arr.length; i++) {
           for (let j = 0; j < arr.length - i - 1; j++) {
               if (arr[j] > arr[j + 1]) {
                   [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];  // Swap
               }
           }
       }
       return arr;
   }
   ```

10. **Merge Sort** (Divide and Conquer):
    - **Time Complexity**: O(n log n)

    **JavaScript**:
    ```javascript
    function mergeSort(arr) {
        if (arr.length <= 1) return arr;
        const mid = Math.floor(arr.length / 2);
        const left = mergeSort(arr.slice(0, mid));
        const right = mergeSort(arr.slice(mid));
        return merge(left, right);
    }

    function merge(left, right) {
        let result = [], i = 0, j = 0;
        while (i < left.length && j < right.length) {
            if (left[i] < right[j]) result.push(left[i++]);
            else result.push(right[j++]);
        }
        return result.concat(left.slice(i), right.slice(j));
    }
    ```

    **PHP**:
    ```php
    function mergeSort($arr) {
        if (count($arr) <= 1) return $arr;
        $mid = intdiv(count($arr), 2);
        $left = mergeSort(array_slice($arr, 0, $mid));
        $right = mergeSort(array_slice($arr, $mid));
        return merge($left, $right);
    }

    function merge($left, $right) {
        $result = [];
        while (count($left) > 0 && count($right) > 0) {
            if ($left[0] < $right[0]) $result[] = array_shift($left);
            else $result[] = array_shift($right);
        }
        return array_merge($result, $left, $right);
    }
    ```

---

### **Graph Algorithms**

11. **Depth-First Search (DFS)**:
    - **Time Complexity**: O(V + E), where `V` is vertices and `E` is edges.

    **JavaScript**:
    ```javascript
    function dfs(graph, node, visited = new Set()) {
        if (!visited.has(node)) {
            console.log(node);
            visited.add(node);
            for (let neighbor of graph[node]) {
                dfs(graph, neighbor, visited);
            }
        }
    }

    let graph = { A: ['B', 'C'], B: ['A', 'D'], C: ['A', 'E'], D: ['B'], E: ['C'] };
    dfs(graph, 'A');  // Output: A B D C E
    ```

12. **Breadth-First Search (BFS)**:
    - **Time Complexity**: O(V + E)

    **JavaScript**:
    ```javascript
    function bfs(graph, start) {
        let queue = [start];
        let visited = new Set();

        while (queue.length > 0) {
            let node = queue.shift();
            if (!visited.has(node)) {
                console.log(node);
                visited.add(node);
                queue.push(...graph[node]);
            }
        }
    }

    let graph = { A: ['B', 'C'], B: ['A', 'D'], C: ['A', 'E'], D: ['B'], E: ['C'] };
    bfs(graph, 'A');  // Output: A B C D E
    ```

---

### **Time Complexities**

- **Searching in Array/Linked List**: O(n)
- **Searching in BST**: O(log n) (on average)
- **Searching in Hash Table**: O(1) (on average)
- **Sorting**:
  - Merge Sort: O(n log n)
  - Bubble Sort: O(n²)
  - Quicksort: O(n log n) (on average)

---

This summary covers key data structures and algorithms along with their implementations in PHP and JavaScript. Let me know if you'd like more details on any topic!


Let's continue with more key data structures and algorithms, focusing on advanced topics and optimizations, while keeping the explanations and code examples concise.

---

### **Advanced Data Structures**

13. **Heap (Priority Queue)**:
   - **Time Complexity**: Insert - O(log n), Extract-Min/Max - O(log n), Peek - O(1).

   **JavaScript (Min-Heap)**:
   ```javascript
   class MinHeap {
       constructor() {
           this.heap = [];
       }

       insert(val) {
           this.heap.push(val);
           this.bubbleUp();
       }

       bubbleUp() {
           let idx = this.heap.length - 1;
           while (idx > 0) {
               let parentIdx = Math.floor((idx - 1) / 2);
               if (this.heap[idx] >= this.heap[parentIdx]) break;
               [this.heap[idx], this.heap[parentIdx]] = [this.heap[parentIdx], this.heap[idx]];
               idx = parentIdx;
           }
       }

       extractMin() {
           if (this.heap.length === 0) return null;
           const min = this.heap[0];
           const end = this.heap.pop();
           if (this.heap.length > 0) {
               this.heap[0] = end;
               this.sinkDown();
           }
           return min;
       }

       sinkDown() {
           let idx = 0;
           const length = this.heap.length;
           while (true) {
               let leftIdx = 2 * idx + 1;
               let rightIdx = 2 * idx + 2;
               let smallest = idx;
               if (leftIdx < length && this.heap[leftIdx] < this.heap[smallest]) {
                   smallest = leftIdx;
               }
               if (rightIdx < length && this.heap[rightIdx] < this.heap[smallest]) {
                   smallest = rightIdx;
               }
               if (smallest === idx) break;
               [this.heap[idx], this.heap[smallest]] = [this.heap[smallest], this.heap[idx]];
               idx = smallest;
           }
       }
   }

   let heap = new MinHeap();
   heap.insert(3);
   heap.insert(1);
   heap.insert(2);
   console.log(heap.extractMin());  // Output: 1
   ```

---

14. **Balanced Binary Search Tree (AVL Tree)**:
   - **Time Complexity**: Search/Insert/Delete - O(log n).
   - AVL Tree ensures that the tree remains balanced after every insertion/deletion.

---

15. **Graph Representations**:
   - **Adjacency Matrix**: O(V²) for space. Useful for dense graphs.
   - **Adjacency List**: O(V + E) for space. Useful for sparse graphs.

16. **Disjoint Set (Union-Find)**:
   - **Time Complexity**: Union/Find - O(α(n)) where α is the inverse Ackermann function.

   **JavaScript (Union-Find)**:
   ```javascript
   class UnionFind {
       constructor(n) {
           this.parent = Array(n).fill(0).map((_, i) => i);
           this.rank = Array(n).fill(0);
       }

       find(x) {
           if (this.parent[x] !== x) {
               this.parent[x] = this.find(this.parent[x]); // Path compression
           }
           return this.parent[x];
       }

       union(x, y) {
           const rootX = this.find(x);
           const rootY = this.find(y);

           if (rootX !== rootY) {
               if (this.rank[rootX] > this.rank[rootY]) {
                   this.parent[rootY] = rootX;
               } else if (this.rank[rootX] < this.rank[rootY]) {
                   this.parent[rootX] = rootY;
               } else {
                   this.parent[rootY] = rootX;
                   this.rank[rootX]++;
               }
           }
       }
   }

   const uf = new UnionFind(5);
   uf.union(0, 1);
   uf.union(2, 3);
   console.log(uf.find(1)); // Output: 0
   console.log(uf.find(3)); // Output: 2
   ```

---

### **Algorithm Optimization Techniques**

17. **Dynamic Programming (DP)**:
   - Store intermediate results to avoid redundant calculations.
   - **Time Complexity**: O(n) if using memoization or tabulation.

18. **Memoization**:
   - **Time Complexity**: O(n) for problems like Fibonacci.

   **JavaScript (Fibonacci with Memoization)**:
   ```javascript
   function fib(n, memo = {}) {
       if (n in memo) return memo[n];
       if (n <= 2) return 1;
       memo[n] = fib(n - 1, memo) + fib(n - 2, memo);
       return memo[n];
   }

   console.log(fib(10));  // Output: 55
   ```

---

19. **Greedy Algorithm**:
   - Make the locally optimal choice at each step.
   - **Time Complexity**: Depends on the problem.

   **JavaScript (Activity Selection)**:
   ```javascript
   function activitySelection(activities) {
       activities.sort((a, b) => a[1] - b[1]);  // Sort by finish time
       let selected = [activities[0]];
       let lastFinishTime = activities[0][1];

       for (let i = 1; i < activities.length; i++) {
           if (activities[i][0] >= lastFinishTime) {
               selected.push(activities[i]);
               lastFinishTime = activities[i][1];
           }
       }

       return selected;
   }

   const activities = [[1, 3], [2, 5], [4, 6], [7, 8]];
   console.log(activitySelection(activities));  // Output: [[1, 3], [4, 6], [7, 8]]
   ```

---

20. **Backtracking**:
   - A general algorithm for finding all (or some) solutions to computational problems.
   - **Example**: Solving puzzles like Sudoku, N-Queens.

   **JavaScript (N-Queens Backtracking)**:
   ```javascript
   function solveNQueens(n) {
       const results = [];
       const board = Array(n).fill().map(() => Array(n).fill('.'));

       function isSafe(row, col) {
           for (let i = 0; i < row; i++) {
               if (board[i][col] === 'Q') return false;
               if (col - (row - i) >= 0 && board[i][col - (row - i)] === 'Q') return false;
               if (col + (row - i) < n && board[i][col + (row - i)] === 'Q') return false;
           }
           return true;
       }

       function backtrack(row = 0) {
           if (row === n) {
               results.push(board.map(r => r.join('')));
               return;
           }

           for (let col = 0; col < n; col++) {
               if (isSafe(row, col)) {
                   board[row][col] = 'Q';
                   backtrack(row + 1);
                   board[row][col] = '.';  // Backtrack
               }
           }
       }

       backtrack();
       return results;
   }

   console.log(solveNQueens(4));  // Output: Solutions for 4-Queens problem
   ```

---

### **Advanced Sorting Algorithms**

21. **QuickSort** (Divide and Conquer):
   - **Time Complexity**: O(n log n) on average, O(n²) in worst-case.

   **JavaScript**:
   ```javascript
   function quicksort(arr) {
       if (arr.length <= 1) return arr;
       let pivot = arr[0];
       let left = arr.filter(x => x < pivot);
       let right = arr.filter(x => x > pivot);
       return [...quicksort(left), pivot, ...quicksort(right)];
   }

   console.log(quicksort([3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]));
   ```

22. **HeapSort**:
   - **Time Complexity**: O(n log n), sorted in-place.

   **JavaScript (Heap Sort)**:
   ```javascript
   function heapSort(arr) {
       let n = arr.length;

       for (let i = Math.floor(n / 2) - 1; i >= 0; i--) heapify(arr, n, i);
       for (let i = n - 1; i > 0; i--) {
           [arr[0], arr[i]] = [arr[i], arr[0]];  // Swap
           heapify(arr, i, 0);
       }
       return arr;
   }

function heapify(arr, n, i) {
    let largest = i;
    let left = 2 * i + 1;
    let right = 2 * i + 2;

    if (left < n && arr[left] > arr[largest]) largest = left;
    if (right < n && arr[right] > arr[largest]) largest = right;

    if (largest !== i) {
        [arr[i], arr[largest]] = [arr[largest], arr[i]];  // Swap
        heapify(arr, n, largest);
    }
}

console.log(heapSort([3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]));


Absolutely! Let's continue with more advanced concepts, algorithms, and optimizations in **data structures** and **algorithms**. I'll keep it short, focusing on practical examples in both **PHP** and **JavaScript**.

---

### **More Advanced Algorithms and Data Structures**

---

### **23. Dijkstra's Algorithm (Shortest Path in Weighted Graph)**

- **Time Complexity**: O((V + E) log V) with a priority queue (min-heap).

**JavaScript (Dijkstra's Algorithm)**:
```javascript
function dijkstra(graph, start) {
    let dist = {};
    let prev = {};
    let pq = new MinHeap();

    // Initialize distances and priority queue
    Object.keys(graph).forEach(node => {
        dist[node] = Infinity;
        prev[node] = null;
        pq.insert(node, Infinity);
    });
    dist[start] = 0;
    pq.insert(start, 0);

    while (!pq.isEmpty()) {
        let u = pq.extractMin();
        if (dist[u] === Infinity) break;

        graph[u].forEach(([v, weight]) => {
            let alt = dist[u] + weight;
            if (alt < dist[v]) {
                dist[v] = alt;
                prev[v] = u;
                pq.insert(v, alt);
            }
        });
    }

    return { dist, prev };
}

class MinHeap {
    constructor() {
        this.heap = [];
    }
    insert(node, priority) {
        this.heap.push({ node, priority });
        this.heapifyUp();
    }
    extractMin() {
        const min = this.heap[0];
        const end = this.heap.pop();
        if (this.heap.length > 0) {
            this.heap[0] = end;
            this.heapifyDown();
        }
        return min.node;
    }
    heapifyUp() {
        let index = this.heap.length - 1;
        while (index > 0) {
            let parentIndex = Math.floor((index - 1) / 2);
            if (this.heap[index].priority < this.heap[parentIndex].priority) {
                [this.heap[index], this.heap[parentIndex]] = [this.heap[parentIndex], this.heap[index]];
                index = parentIndex;
            } else break;
        }
    }
    heapifyDown() {
        let index = 0;
        const length = this.heap.length;
        while (index < length) {
            let left = 2 * index + 1;
            let right = 2 * index + 2;
            let smallest = index;

            if (left < length && this.heap[left].priority < this.heap[smallest].priority) {
                smallest = left;
            }
            if (right < length && this.heap[right].priority < this.heap[smallest].priority) {
                smallest = right;
            }
            if (smallest === index) break;

            [this.heap[index], this.heap[smallest]] = [this.heap[smallest], this.heap[index]];
            index = smallest;
        }
    }
}

let graph = {
    A: [['B', 1], ['C', 4]],
    B: [['A', 1], ['C', 2], ['D', 5]],
    C: [['A', 4], ['B', 2], ['D', 1]],
    D: [['B', 5], ['C', 1]]
};

console.log(dijkstra(graph, 'A'));
```

---

### **24. Bellman-Ford Algorithm (Shortest Path for Graphs with Negative Weights)**

- **Time Complexity**: O(V * E).

**JavaScript (Bellman-Ford Algorithm)**:
```javascript
function bellmanFord(graph, start) {
    let dist = {};
    let edges = [];

    // Initialize distances
    Object.keys(graph).forEach(node => {
        dist[node] = Infinity;
        graph[node].forEach(([v, w]) => edges.push([node, v, w]));
    });
    dist[start] = 0;

    // Relax edges V-1 times
    for (let i = 1; i < Object.keys(graph).length; i++) {
        for (let [u, v, w] of edges) {
            if (dist[u] + w < dist[v]) {
                dist[v] = dist[u] + w;
            }
        }
    }

    // Check for negative weight cycles
    for (let [u, v, w] of edges) {
        if (dist[u] + w < dist[v]) {
            throw new Error("Graph contains a negative-weight cycle");
        }
    }

    return dist;
}

let graph = {
    A: [['B', 1], ['C', 4]],
    B: [['A', 1], ['C', 2], ['D', 5]],
    C: [['A', 4], ['B', 2], ['D', 1]],
    D: [['B', 5], ['C', 1]]
};

console.log(bellmanFord(graph, 'A'));
```

---

### **25. Topological Sort (Directed Acyclic Graph)**

- **Time Complexity**: O(V + E).

**JavaScript (Topological Sort)**:
```javascript
function topologicalSort(graph) {
    let visited = new Set();
    let result = [];

    function dfs(node) {
        if (visited.has(node)) return;
        visited.add(node);

        if (graph[node]) {
            for (let neighbor of graph[node]) {
                dfs(neighbor);
            }
        }

        result.push(node);
    }

    for (let node of Object.keys(graph)) {
        if (!visited.has(node)) {
            dfs(node);
        }
    }

    return result.reverse();
}

let graph = {
    A: ['B', 'C'],
    B: ['D'],
    C: ['D'],
    D: []
};

console.log(topologicalSort(graph));  // Output: ['A', 'C', 'B', 'D']
```

---

### **26. Kruskal's Algorithm (Minimum Spanning Tree)**

- **Time Complexity**: O(E log E), using Union-Find.

**JavaScript (Kruskal's Algorithm)**:
```javascript
class UnionFind {
    constructor(n) {
        this.parent = Array(n).fill(0).map((_, i) => i);
        this.rank = Array(n).fill(0);
    }

    find(x) {
        if (this.parent[x] !== x) {
            this.parent[x] = this.find(this.parent[x]);
        }
        return this.parent[x];
    }

    union(x, y) {
        let rootX = this.find(x);
        let rootY = this.find(y);

        if (rootX !== rootY) {
            if (this.rank[rootX] > this.rank[rootY]) {
                this.parent[rootY] = rootX;
            } else if (this.rank[rootX] < this.rank[rootY]) {
                this.parent[rootX] = rootY;
            } else {
                this.parent[rootY] = rootX;
                this.rank[rootX]++;
            }
        }
    }
}

function kruskal(edges, n) {
    edges.sort((a, b) => a[2] - b[2]); // Sort by weight
    let uf = new UnionFind(n);
    let result = [];

    for (let [u, v, w] of edges) {
        if (uf.find(u) !== uf.find(v)) {
            uf.union(u, v);
            result.push([u, v, w]);
        }
    }

    return result;
}

let edges = [
    [0, 1, 1], [0, 2, 3], [1, 2, 1], [1, 3, 6], [2, 3, 2]
];
console.log(kruskal(edges, 4));
```

---

### **27. Floyd-Warshall Algorithm (All-Pairs Shortest Path)**

- **Time Complexity**: O(V³).

**JavaScript (Floyd-Warshall Algorithm)**:
```javascript
function floydWarshall(graph) {
    let dist = JSON.parse(JSON.stringify(graph));

    for (let k in graph) {
        for (let i in graph) {
            for (let j in graph) {
                if (dist[i][k] !== Infinity && dist[k][j] !== Infinity) {
                    dist[i][j] = Math.min(dist[i][j], dist[i][k] + dist[k][j]);
                }
            }
        }
    }

    return dist;
}

let graph = {
    A: {A: 0, B: 3, C: Infinity, D: 7},
    B: {A: Infinity, B: 0, C: 1, D: 2},
    C: {A: Infinity, B: Infinity, C: 0, D: 3},
    D: {A: Infinity, B: Infinity, C: Infinity, D: 0}
};

console.log(floydWarshall(graph));
```

---

### **28. Rabin-Karp Algorithm (String Matching)**

- **Time Complexity**: O(n + m) on average (where n = text length, m = pattern length).

**JavaScript (Rabin-Karp Algorithm)**:
```javascript
function rabinKarp(text, pattern) {
    let m = pattern.length, n = text.length;
    let d = 256;  // Number of characters in the input alphabet
    let q = 101;  // A prime number
    let h = Math.pow(d, m - 1) % q;
    let p = 0, t = 0;

    // Calculate hash values for pattern and first window of text
    for (let i = 0; i < m; i++) {
        p = (p * d + pattern.charCodeAt(i)) % q;
        t = (t * d + text.charCodeAt(i)) % q;
    }

    for (let i = 0; i <= n - m; i++) {
        if (p === t) {
            if (text.slice(i, i + m) === pattern) {
                console.log(`Pattern found at index ${i}`);
            }
        }
        if (i < n - m) {
            t = (d * (t - text.charCodeAt(i) * h) + text.charCodeAt(i + m)) % q;
            if (t < 0) t += q;
        }
    }
}

rabinKarp('ABABDABACDABABCABAB', 'ABABCABAB');
