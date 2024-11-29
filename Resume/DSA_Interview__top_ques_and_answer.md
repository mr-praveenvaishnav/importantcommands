Got it! I'll start again, focusing only on PHP and JavaScript examples for the top 100 Data Structures and Algorithms (DSA) interview questions.

---


### **Level 0: Basic Understanding and Simple Problems**

1. **What is an array?**

   - **Definition**: An array is a collection of elements stored at contiguous memory locations, where each element can be accessed using an index.

2. **What is the difference between an array and a linked list?**

   - **Array**: Fixed size, elements stored in contiguous memory.
   - **Linked List**: Dynamic size, elements (nodes) contain data and a reference to the next node.

3. **What is a stack?**

   - **Definition**: A stack is a data structure that follows the Last-In-First-Out (LIFO) principle. Elements are added (push) and removed (pop) from the top.

4. **What is a queue?**

   - **Definition**: A queue is a data structure that follows the First-In-First-Out (FIFO) principle. Elements are added (enqueue) at the rear and removed (dequeue) from the front.

5. **Write a program to reverse an array in JavaScript:**
   ```javascript
   function reverseArray(arr) {
       return arr.reverse();
   }
   console.log(reverseArray([1, 2, 3, 4, 5])); // Output: [5, 4, 3, 2, 1]
   ```

6. **Write a program to reverse an array in PHP:**
   ```php
   function reverseArray($arr) {
       return array_reverse($arr);
   }
   print_r(reverseArray([1, 2, 3, 4, 5])); // Output: [5, 4, 3, 2, 1]
   ```

7. **What is a binary search?**

   - **Definition**: Binary search is an efficient algorithm to find an element in a sorted array. It repeatedly divides the search space into halves until the element is found.

8. **Write a binary search in JavaScript:**
   ```javascript
   function binarySearch(arr, target) {
       let low = 0;
       let high = arr.length - 1;

       while (low <= high) {
           let mid = Math.floor((low + high) / 2);

           if (arr[mid] === target) return mid;
           if (arr[mid] < target) low = mid + 1;
           else high = mid - 1;
       }
       return -1;
   }
   console.log(binarySearch([1, 2, 3, 4, 5], 3)); // Output: 2
   ```

9. **Write a binary search in PHP:**
   ```php
   function binarySearch($arr, $target) {
       $low = 0;
       $high = count($arr) - 1;

       while ($low <= $high) {
           $mid = floor(($low + $high) / 2);

           if ($arr[$mid] == $target) return $mid;
           if ($arr[$mid] < $target) $low = $mid + 1;
           else $high = $mid - 1;
       }
       return -1;
   }
   echo binarySearch([1, 2, 3, 4, 5], 3); // Output: 2
   ```

---

### **Level 1: Intermediate Problems**

10. **What is a stack's time complexity for push and pop operations?**

    - **Answer**: Both push and pop operations in a stack are **O(1)** (constant time).

11. **Write a program to implement a stack in JavaScript using arrays:**
    ```javascript
    class Stack {
        constructor() {
            this.items = [];
        }

        push(item) {
            this.items.push(item);
        }

        pop() {
            return this.items.pop();
        }

        peek() {
            return this.items[this.items.length - 1];
        }

        isEmpty() {
            return this.items.length === 0;
        }
    }

    const stack = new Stack();
    stack.push(10);
    stack.push(20);
    console.log(stack.pop()); // Output: 20
    ```

12. **Write a program to implement a queue in JavaScript using arrays:**
    ```javascript
    class Queue {
        constructor() {
            this.items = [];
        }

        enqueue(item) {
            this.items.push(item);
        }

        dequeue() {
            return this.items.shift();
        }

        front() {
            return this.items[0];
        }

        isEmpty() {
            return this.items.length === 0;
        }
    }

    const queue = new Queue();
    queue.enqueue(10);
    queue.enqueue(20);
    console.log(queue.dequeue()); // Output: 10
    ```

13. **Write a program to implement a stack using two queues in PHP:**
    ```php
    class Stack {
        private $queue1 = [];
        private $queue2 = [];

        public function push($item) {
            array_push($this->queue1, $item);
        }

        public function pop() {
            if (empty($this->queue1)) {
                return null;
            }

            while (count($this->queue1) > 1) {
                array_push($this->queue2, array_shift($this->queue1));
            }
            $popped = array_shift($this->queue1);
            $this->queue1 = $this->queue2;
            $this->queue2 = [];
            return $popped;
        }
    }

    $stack = new Stack();
    $stack->push(10);
    $stack->push(20);
    echo $stack->pop(); // Output: 20
    ```

14. **Write a program to implement a stack using two queues in JavaScript:**
    ```javascript
    class Stack {
        constructor() {
            this.queue1 = [];
            this.queue2 = [];
        }

        push(item) {
            this.queue1.push(item);
        }

        pop() {
            if (this.queue1.length === 0) {
                return null;
            }
            while (this.queue1.length > 1) {
                this.queue2.push(this.queue1.shift());
            }
            const popped = this.queue1.shift();
            [this.queue1, this.queue2] = [this.queue2, this.queue1];
            return popped;
        }
    }

    const stack = new Stack();
    stack.push(10);
    stack.push(20);
    console.log(stack.pop()); // Output: 20
    ```

15. **What is the time complexity of binary search?**
    - **Answer**: O(log n), where n is the number of elements in the array.

16. **What is a doubly linked list?**

    - **Definition**: A doubly linked list is a type of linked list where each node has two pointers, one pointing to the next node and one pointing to the previous node.

17. **Write a program to detect a cycle in a linked list using JavaScript:**
    ```javascript
    class ListNode {
        constructor(value) {
            this.value = value;
            this.next = null;
        }
    }

    function hasCycle(head) {
        let slow = head, fast = head;
        while (fast !== null && fast.next !== null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow === fast) {
                return true;
            }
        }
        return false;
    }
    ```

18. **Write a program to detect a cycle in a linked list using PHP:**
    ```php
    class ListNode {
        public $value;
        public $next = null;
        public function __construct($value) {
            $this->value = $value;
        }
    }

    function hasCycle($head) {
        $slow = $head;
        $fast = $head;

        while ($fast !== null && $fast->next !== null) {
            $slow = $slow->next;
            $fast = $fast->next->next;
            if ($slow === $fast) {
                return true;
            }
        }
        return false;
    }
    ```

---

### **Level 2: Advanced Data Structures and Algorithms**

19. **What is a binary tree?**

    - **Definition**: A binary tree is a tree data structure where each node has at most two children: a left child and a right child.

20. **Write a program to perform an inorder traversal of a binary tree in JavaScript:**
    ```javascript
    function inorderTraversal(root) {
        if (root) {
            inorderTraversal(root.left);
            console.log(root.value);
            inorderTraversal(root.right);
        }
    }
    ```

21. **Write a program to perform an inorder traversal of a binary tree in PHP:**
    ```php
    function inorderTraversal($root) {
        if ($root) {
            inorderTraversal($root->left);
            echo $root->value . ' ';
            inorderTraversal($root->right);
        }
    }
    ```

22. **What is the time complexity of an inorder traversal of a binary tree?**
    - **Answer**: O(n), where n is the number of nodes in the tree.

23. **What is a heap?**

    - **Definition**: A heap is a complete binary tree that satisfies the heap property. In a max heap, the parent node is greater than or equal to its children, and in a min heap, the parent node is less than or equal to its




    Sure! Continuing from where we left off:

---

### **Level 2: Advanced Data Structures and Algorithms (continued)**

24. **What is a heap?**

   - **Definition**: A heap is a complete binary tree that satisfies the heap property. In a **max-heap**, the parent node is greater than or equal to its children, and in a **min-heap**, the parent node is less than or equal to its children. Heaps are typically implemented using arrays.

25. **Write a program to implement a max-heap using an array in JavaScript:**
    ```javascript
    function maxHeapify(arr, n, i) {
        let largest = i;
        const left = 2 * i + 1;
        const right = 2 * i + 2;

        if (left < n && arr[left] > arr[largest]) {
            largest = left;
        }

        if (right < n && arr[right] > arr[largest]) {
            largest = right;
        }

        if (largest !== i) {
            [arr[i], arr[largest]] = [arr[largest], arr[i]];
            maxHeapify(arr, n, largest);
        }
    }

    function buildMaxHeap(arr) {
        const n = arr.length;
        for (let i = Math.floor(n / 2) - 1; i >= 0; i--) {
            maxHeapify(arr, n, i);
        }
    }

    const arr = [4, 10, 3, 5, 1];
    buildMaxHeap(arr);
    console.log(arr); // Output: [10, 5, 3, 4, 1]
    ```

26. **Write a program to implement a max-heap using an array in PHP:**
    ```php
    function maxHeapify(&$arr, $n, $i) {
        $largest = $i;
        $left = 2 * $i + 1;
        $right = 2 * $i + 2;

        if ($left < $n && $arr[$left] > $arr[$largest]) {
            $largest = $left;
        }

        if ($right < $n && $arr[$right] > $arr[$largest]) {
            $largest = $right;
        }

        if ($largest != $i) {
            list($arr[$i], $arr[$largest]) = array($arr[$largest], $arr[$i]);
            maxHeapify($arr, $n, $largest);
        }
    }

    function buildMaxHeap(&$arr) {
        $n = count($arr);
        for ($i = floor($n / 2) - 1; $i >= 0; $i--) {
            maxHeapify($arr, $n, $i);
        }
    }

    $arr = [4, 10, 3, 5, 1];
    buildMaxHeap($arr);
    print_r($arr); // Output: [10, 5, 3, 4, 1]
    ```

27. **What is Dijkstra’s Algorithm?**

   - **Definition**: Dijkstra’s algorithm is a graph algorithm used to find the shortest path between nodes in a graph. It uses a greedy approach and a priority queue to select the next node with the smallest tentative distance.

28. **Write a Dijkstra's algorithm implementation in JavaScript (using an array for simplicity):**
    ```javascript
    function dijkstra(graph, start) {
        let dist = {};
        let visited = new Set();
        let pq = new PriorityQueue();

        // Initialize distances
        for (let vertex in graph) {
            dist[vertex] = Infinity;
        }
        dist[start] = 0;

        pq.enqueue([start, 0]);

        while (!pq.isEmpty()) {
            let [vertex, distance] = pq.dequeue();

            if (visited.has(vertex)) continue;
            visited.add(vertex);

            for (let neighbor in graph[vertex]) {
                let newDist = distance + graph[vertex][neighbor];
                if (newDist < dist[neighbor]) {
                    dist[neighbor] = newDist;
                    pq.enqueue([neighbor, newDist]);
                }
            }
        }

        return dist;
    }

    class PriorityQueue {
        constructor() {
            this.items = [];
        }

        enqueue(element) {
            this.items.push(element);
            this.items.sort((a, b) => a[1] - b[1]);
        }

        dequeue() {
            return this.items.shift();
        }

        isEmpty() {
            return this.items.length === 0;
        }
    }

    const graph = {
        A: { B: 4, C: 2 },
        B: { A: 4, C: 5, D: 10 },
        C: { A: 2, B: 5, D: 3 },
        D: { B: 10, C: 3 },
    };

    console.log(dijkstra(graph, 'A')); // Output: { A: 0, B: 4, C: 2, D: 5 }
    ```

29. **Write Dijkstra's algorithm in PHP:**
    ```php
    class PriorityQueue {
        private $items = [];

        public function enqueue($element) {
            $this->items[] = $element;
            usort($this->items, function ($a, $b) {
                return $a[1] - $b[1];
            });
        }

        public function dequeue() {
            return array_shift($this->items);
        }

        public function isEmpty() {
            return empty($this->items);
        }
    }

    function dijkstra($graph, $start) {
        $dist = [];
        $visited = [];
        $pq = new PriorityQueue();

        foreach ($graph as $vertex => $edges) {
            $dist[$vertex] = PHP_INT_MAX;
            $visited[$vertex] = false;
        }

        $dist[$start] = 0;
        $pq->enqueue([$start, 0]);

        while (!$pq->isEmpty()) {
            list($vertex, $distance) = $pq->dequeue();

            if ($visited[$vertex]) continue;
            $visited[$vertex] = true;

            foreach ($graph[$vertex] as $neighbor => $weight) {
                $newDist = $distance + $weight;
                if ($newDist < $dist[$neighbor]) {
                    $dist[$neighbor] = $newDist;
                    $pq->enqueue([$neighbor, $newDist]);
                }
            }
        }

        return $dist;
    }

    $graph = [
        'A' => ['B' => 4, 'C' => 2],
        'B' => ['A' => 4, 'C' => 5, 'D' => 10],
        'C' => ['A' => 2, 'B' => 5, 'D' => 3],
        'D' => ['B' => 10, 'C' => 3],
    ];

    print_r(dijkstra($graph, 'A')); // Output: Array ( [A] => 0 [B] => 4 [C] => 2 [D] => 5 )
    ```

30. **What is a trie?**

   - **Definition**: A trie (prefix tree) is a special type of tree used to store strings. Each node represents a character, and paths from the root represent the string's characters.

31. **Write a trie implementation in JavaScript:**
    ```javascript
    class TrieNode {
        constructor() {
            this.children = {};
            this.isEndOfWord = false;
        }
    }

    class Trie {
        constructor() {
            this.root = new TrieNode();
        }

        insert(word) {
            let node = this.root;
            for (let char of word) {
                if (!node.children[char]) {
                    node.children[char] = new TrieNode();
                }
                node = node.children[char];
            }
            node.isEndOfWord = true;
        }

        search(word) {
            let node = this.root;
            for (let char of word) {
                if (!node.children[char]) {
                    return false;
                }
                node = node.children[char];
            }
            return node.isEndOfWord;
        }
    }

    const trie = new Trie();
    trie.insert("apple");
    console.log(trie.search("apple")); // Output: true
    console.log(trie.search("app")); // Output: false
    ```

32. **Write a trie implementation in PHP:**
    ```php
   class TrieNode {
    public $children = [];
    public $isEndOfWord = false;
}

class Trie {
    private $root;

    public function __construct() {
        $this->root = new TrieNode();
    }

    public function insert($word) {
        $node = $this->root;
        for ($i = 0; $i < strlen($word); $i++) {
            $char = $word[$i];
            if (!isset($node->children[$char])) {
                $node->children[$char] = new TrieNode();
            }
            $node = $node->children[$char];
        }
        $node->isEndOfWord = true;
    }

    public function search($word) {
        $node = $this->root;
        for ($i = 0; $i < strlen($word); $i++) {
            $char = $word[$i];
            if (!isset($node->children[$char])) {
                return false;
            }
            $node = $node->children[$char];
        }
        return $node->isEndOfWord;
    }
}

$trie = new Trie();
$trie->insert("apple");
echo $trie->search("apple"); // Output: 1 (true)
echo $trie->search("app");   // Output:  (false)

Sure! Continuing from where we left off:

---

### **Level 2: Advanced Data Structures and Algorithms (continued)**

32. **Write a trie implementation in PHP (continued):**

   ```php
   class TrieNode {
       public $children = [];
       public $isEndOfWord = false;
   }

   class Trie {
       private $root;

       public function __construct() {
           $this->root = new TrieNode();
       }

       public function insert($word) {
           $node = $this->root;
           for ($i = 0; $i < strlen($word); $i++) {
               $char = $word[$i];
               if (!isset($node->children[$char])) {
                   $node->children[$char] = new TrieNode();
               }
               $node = $node->children[$char];
           }
           $node->isEndOfWord = true;
       }

       public function search($word) {
           $node = $this->root;
           for ($i = 0; $i < strlen($word); $i++) {
               $char = $word[$i];
               if (!isset($node->children[$char])) {
                   return false;
               }
               $node = $node->children[$char];
           }
           return $node->isEndOfWord;
       }
   }

   $trie = new Trie();
   $trie->insert("apple");
   echo $trie->search("apple"); // Output: 1 (true)
   echo $trie->search("app");   // Output:  (false)
   ```

33. **What is a hash table?**

   - **Definition**: A hash table (or hash map) is a data structure that maps keys to values. It uses a hash function to compute an index into an array of buckets, where the desired value can be found.

34. **Write a program to implement a hash table in JavaScript:**

   ```javascript
   class HashTable {
       constructor(size) {
           this.table = new Array(size);
       }

       _hash(key) {
           let hash = 0;
           for (let i = 0; i < key.length; i++) {
               hash = (hash + key.charCodeAt(i)) % this.table.length;
           }
           return hash;
       }

       insert(key, value) {
           const index = this._hash(key);
           if (!this.table[index]) {
               this.table[index] = [];
           }
           this.table[index].push([key, value]);
       }

       get(key) {
           const index = this._hash(key);
           if (!this.table[index]) return undefined;
           for (let i = 0; i < this.table[index].length; i++) {
               if (this.table[index][i][0] === key) {
                   return this.table[index][i][1];
               }
           }
           return undefined;
       }

       remove(key) {
           const index = this._hash(key);
           if (!this.table[index]) return;
           for (let i = 0; i < this.table[index].length; i++) {
               if (this.table[index][i][0] === key) {
                   this.table[index].splice(i, 1);
                   return;
               }
           }
       }
   }

   const hashTable = new HashTable(10);
   hashTable.insert("name", "Alice");
   console.log(hashTable.get("name")); // Output: Alice
   hashTable.remove("name");
   console.log(hashTable.get("name")); // Output: undefined
   ```

35. **Write a program to implement a hash table in PHP:**

   ```php
   class HashTable {
       private $table = [];

       private function hash($key) {
           $hash = 0;
           for ($i = 0; $i < strlen($key); $i++) {
               $hash = ($hash + ord($key[$i])) % count($this->table);
           }
           return $hash;
       }

       public function insert($key, $value) {
           $index = $this->hash($key);
           if (!isset($this->table[$index])) {
               $this->table[$index] = [];
           }
           $this->table[$index][] = [$key, $value];
       }

       public function get($key) {
           $index = $this->hash($key);
           if (!isset($this->table[$index])) {
               return null;
           }
           foreach ($this->table[$index] as $pair) {
               if ($pair[0] === $key) {
                   return $pair[1];
               }
           }
           return null;
       }

       public function remove($key) {
           $index = $this->hash($key);
           if (!isset($this->table[$index])) {
               return;
           }
           foreach ($this->table[$index] as $i => $pair) {
               if ($pair[0] === $key) {
                   unset($this->table[$index][$i]);
                   return;
               }
           }
       }
   }

   $hashTable = new HashTable();
   $hashTable->insert("name", "Alice");
   echo $hashTable->get("name"); // Output: Alice
   $hashTable->remove("name");
   echo $hashTable->get("name"); // Output: null
   ```

36. **What is the time complexity of searching, inserting, and deleting in a hash table?**
   - **Answer**: The average time complexity for searching, inserting, and deleting in a hash table is **O(1)**, but in the worst case (when collisions are high), it can degrade to **O(n)**.

---

### **Level 3: High-Level Concepts and Complex Problems**

37. **What is a graph?**

   - **Definition**: A graph is a collection of nodes (vertices) and edges (connections) between them. Graphs can be classified as directed (where edges have direction) or undirected.

38. **Write a program to implement BFS (Breadth-First Search) in JavaScript:**

   ```javascript
   function bfs(graph, start) {
       let visited = new Set();
       let queue = [start];

       while (queue.length > 0) {
           let node = queue.shift();
           if (!visited.has(node)) {
               console.log(node);
               visited.add(node);
               queue.push(...graph[node]);
           }
       }
   }

   const graph = {
       A: ['B', 'C'],
       B: ['A', 'D', 'E'],
       C: ['A', 'F'],
       D: ['B'],
       E: ['B'],
       F: ['C'],
   };

   bfs(graph, 'A'); // Output: A B C D E F
   ```

39. **Write a program to implement BFS (Breadth-First Search) in PHP:**

   ```php
   function bfs($graph, $start) {
       $visited = [];
       $queue = [$start];

       while (!empty($queue)) {
           $node = array_shift($queue);
           if (!in_array($node, $visited)) {
               echo $node . ' ';
               $visited[] = $node;
               foreach ($graph[$node] as $neighbor) {
                   if (!in_array($neighbor, $visited)) {
                       $queue[] = $neighbor;
                   }
               }
           }
       }
   }

   $graph = [
       'A' => ['B', 'C'],
       'B' => ['A', 'D', 'E'],
       'C' => ['A', 'F'],
       'D' => ['B'],
       'E' => ['B'],
       'F' => ['C'],
   ];

   bfs($graph, 'A'); // Output: A B C D E F
   ```

40. **What is a depth-first search (DFS)?**

   - **Definition**: DFS is an algorithm used to traverse or search through a graph. It starts at a node and explores as far as possible along each branch before backtracking.

41. **Write a program to implement DFS (Depth-First Search) in JavaScript:**

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

   const graph = {
       A: ['B', 'C'],
       B: ['A', 'D', 'E'],
       C: ['A', 'F'],
       D: ['B'],
       E: ['B'],
       F: ['C'],
   };

   dfs(graph, 'A'); // Output: A B D E C F
   ```

42. **Write a program to implement DFS (Depth-First Search) in PHP:**

   ```php
   function dfs($graph, $node, &$visited = []) {
       if (!in_array($node, $visited)) {
           echo $node . ' ';
           $visited[] = $node;
           foreach ($graph[$node] as $neighbor) {
               dfs($graph, $neighbor, $visited);
           }
       }
   }

   $graph = [
       'A' => ['B', 'C'],
       'B' => ['A', 'D', 'E'],
       'C' => ['A', 'F'],
       'D' => ['B'],
       'E' => ['B'],
       'F' => ['C'],
   ];

   dfs($graph, 'A'); // Output: A B D E C F
   ```



---

This concludes a selection of interview questions on Data Structures and Algorithms, from beginner to advanced levels, using both JavaScript and PHP examples. Let me know if you'd like to dive deeper into any specific topic!


Certainly! Let's continue with more advanced concepts, including algorithm optimizations and more complex data structures.

---

### **Level 3: High-Level Concepts and Complex Problems (continued)**

43. **What is a dynamic programming (DP) approach?**

   - **Definition**: Dynamic programming is an optimization technique used to solve problems by breaking them down into simpler subproblems. It stores the results of subproblems to avoid redundant calculations. DP is typically used in problems with overlapping subproblems and optimal substructure, such as in the Fibonacci series, knapsack problem, etc.

44. **Write a program to find the nth Fibonacci number using dynamic programming in JavaScript:**

   ```javascript
   function fibonacci(n) {
       let dp = [0, 1];
       for (let i = 2; i <= n; i++) {
           dp[i] = dp[i - 1] + dp[i - 2];
       }
       return dp[n];
   }

   console.log(fibonacci(10)); // Output: 55
   ```

45. **Write a program to find the nth Fibonacci number using dynamic programming in PHP:**

   ```php
   function fibonacci($n) {
       $dp = [0, 1];
       for ($i = 2; $i <= $n; $i++) {
           $dp[$i] = $dp[$i - 1] + $dp[$i - 2];
       }
       return $dp[$n];
   }

   echo fibonacci(10); // Output: 55
   ```

46. **What is the difference between recursion and dynamic programming?**

   - **Answer**: Recursion solves problems by breaking them down into smaller subproblems, typically without remembering the previous results, which can lead to repeated calculations. Dynamic programming, on the other hand, stores the results of subproblems (memoization or tabulation), avoiding redundant computations.

47. **What is the time complexity of the Fibonacci problem using recursion and dynamic programming?**

   - **Answer**: 
     - **Recursion**: O(2^n) due to the repeated calculations of the same subproblems.
     - **Dynamic Programming (Tabulation)**: O(n) time complexity, as it only computes each subproblem once and stores the results.

48. **What is a greedy algorithm?**

   - **Definition**: A greedy algorithm makes the optimal choice at each step, with the hope of finding the global optimum. It doesn’t always guarantee the optimal solution for all problems, but it works well for problems like Huffman coding, interval scheduling, and the coin change problem.

49. **Write a program to solve the coin change problem using a greedy algorithm in JavaScript:**

   ```javascript
   function coinChange(coins, amount) {
       coins.sort((a, b) => b - a);  // Sort coins in descending order
       let count = 0;
       for (let coin of coins) {
           if (amount >= coin) {
               count += Math.floor(amount / coin);  // Use as many of this coin as possible
               amount %= coin;
           }
       }
       return amount === 0 ? count : -1;  // If we can't reach 0, return -1
   }

   console.log(coinChange([1, 5, 10, 25], 63)); // Output: 6 (2 * 25 + 1 * 10 + 1 * 5 + 3 * 1)
   ```

50. **Write a program to solve the coin change problem using a greedy algorithm in PHP:**

   ```php
   function coinChange($coins, $amount) {
       rsort($coins);  // Sort coins in descending order
       $count = 0;
       foreach ($coins as $coin) {
           if ($amount >= $coin) {
               $count += intdiv($amount, $coin);  // Use as many of this coin as possible
               $amount %= $coin;
           }
       }
       return $amount === 0 ? $count : -1;  // If we can't reach 0, return -1
   }

   echo coinChange([1, 5, 10, 25], 63); // Output: 6
   ```

51. **What is the time complexity of a greedy algorithm for the coin change problem?**

   - **Answer**: The time complexity is O(n * log n) due to sorting the coins, where `n` is the number of different coins. The iteration through coins takes O(n) time.

52. **What is a divide and conquer algorithm?**

   - **Definition**: Divide and conquer is an algorithmic paradigm where a problem is divided into smaller subproblems, solved independently, and then combined to produce the final result. Merge sort and quicksort are classic examples of divide and conquer algorithms.

53. **Write a program to implement merge sort in JavaScript:**

   ```javascript
   function mergeSort(arr) {
       if (arr.length <= 1) {
           return arr;
       }

       const mid = Math.floor(arr.length / 2);
       const left = mergeSort(arr.slice(0, mid));
       const right = mergeSort(arr.slice(mid));

       return merge(left, right);
   }

   function merge(left, right) {
       let result = [];
       let leftIndex = 0;
       let rightIndex = 0;

       while (leftIndex < left.length && rightIndex < right.length) {
           if (left[leftIndex] < right[rightIndex]) {
               result.push(left[leftIndex]);
               leftIndex++;
           } else {
               result.push(right[rightIndex]);
               rightIndex++;
           }
       }

       return result.concat(left.slice(leftIndex), right.slice(rightIndex));
   }

   console.log(mergeSort([3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5])); 
   // Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
   ```

54. **Write a program to implement merge sort in PHP:**

   ```php
   function mergeSort($arr) {
       if (count($arr) <= 1) {
           return $arr;
       }

       $mid = intdiv(count($arr), 2);
       $left = mergeSort(array_slice($arr, 0, $mid));
       $right = mergeSort(array_slice($arr, $mid));

       return merge($left, $right);
   }

   function merge($left, $right) {
       $result = [];
       $leftIndex = 0;
       $rightIndex = 0;

       while ($leftIndex < count($left) && $rightIndex < count($right)) {
           if ($left[$leftIndex] < $right[$rightIndex]) {
               $result[] = $left[$leftIndex];
               $leftIndex++;
           } else {
               $result[] = $right[$rightIndex];
               $rightIndex++;
           }
       }

       return array_merge($result, array_slice($left, $leftIndex), array_slice($right, $rightIndex));
   }

   print_r(mergeSort([3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]));
   // Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
   ```

55. **What is the time complexity of merge sort?**

   - **Answer**: The time complexity of merge sort is **O(n log n)**, where `n` is the number of elements to be sorted. This is because the array is divided into two halves (O(log n) levels of recursion), and each level requires O(n) time to merge the subarrays.

56. **What is the time complexity of quicksort?**

   - **Answer**: The time complexity of quicksort is **O(n log n)** on average, but in the worst case (when the pivot is poorly chosen), it can degrade to **O(n^2)**.

57. **Write a program to implement quicksort in JavaScript:**

   ```javascript
   function quicksort(arr) {
       if (arr.length <= 1) return arr;

       const pivot = arr[0];
       const left = [];
       const right = [];

       for (let i = 1; i < arr.length; i++) {
           if (arr[i] < pivot) left.push(arr[i]);
           else right.push(arr[i]);
       }

       return [...quicksort(left), pivot, ...quicksort(right)];
   }

   console.log(quicksort([3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5])); 
   // Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
   ```

58. **Write a program to implement quicksort in PHP:**


   ```php
   function quicksort($arr) {
    if (count($arr) <= 1) return $arr;

    $pivot = $arr[0];
    $left = [];
    $right = [];

    for ($i = 1; $i < count($arr); $i++) {
        if ($arr[$i] < $pivot) $left[] = $arr[$i];
        else $right[] = $arr[$i];
    }

    return array_merge(quicksort($left), [$pivot], quicksort($right));
}

print_r(quicksort([3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]));
// Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]





