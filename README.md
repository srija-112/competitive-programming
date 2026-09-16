// Effective Address of 2D Array — Row Major + Binary
# Row Major Effective Address
base = int(input("Enter base address: "))
rows = int(input("Enter number of rows: "))
cols = int(input("Enter number of columns: "))
size = int(input("Enter size of each element: "))
i = int(input("Enter row index: "))
j = int(input("Enter column index: "))

address = base + ((i * cols + j) * size)

print("Effective Address =", address)
print("Address in Binary =", bin(address))


//Height of a Tree
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None


def height(root):
    if root is None:
        return 0

    return 1 + max(height(root.left), height(root.right))


root = Node(1)
root.left = Node(2)
root.right = Node(3)


//Number of Nodes in a Tree
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None


def count_nodes(root):
    if root is None:
        return 0

    return 1 + count_nodes(root.left) + count_nodes(root.right)


root = Node(1)
root.left = Node(2)
root.right = Node(3)
root.left.left = Node(4)
root.left.right = Node(5)

print("Number of Nodes =", count_nodes(root))

root.left.left = Node(4)
root.left.right = Node(5)

print("Height of Tree =", height(root))


//Number of Internal Nodes
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None


def count_internal(root):
    if root is None or (root.left is None and root.right is None):
        return 0

    return 1 + count_internal(root.left) + count_internal(root.right)


root = Node(1)
root.left = Node(2)
root.right = Node(3)
root.left.left = Node(4)
root.left.right = Node(5)

print("Number of Internal Nodes =", count_internal(root))


//Number of Leaf Nodes
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None


def count_leaf(root):
    if root is None:
        return 0

    if root.left is None and root.right is None:
        return 1

    return count_leaf(root.left) + count_leaf(root.right)


root = Node(1)
root.left = Node(2)
root.right = Node(3)
root.left.left = Node(4)
root.left.right = Node(5)

print("Number of Leaf Nodes =", count_leaf(root))


//Binary Search
arr = list(map(int, input("Enter sorted elements: ").split()))
key = int(input("Enter element to search: "))

low = 0
high = len(arr) - 1
found = False

while low <= high:
    mid = (low + high) // 2

    if arr[mid] == key:
        print("Element found at index", mid)
        found = True
        break
    elif arr[mid] < key:
        low = mid + 1
    else:
        high = mid - 1

if not found:
    print("Element not found")


//Effective Address of 1D Array
base = int(input("Enter base address: "))
index = int(input("Enter index: "))
size = int(input("Enter size of each element: "))

address = base + index * size

print("Effective Address =", address)


//Effective Address of 2D Array — Column Major
base = int(input("Enter base address: "))
rows = int(input("Enter number of rows: "))
cols = int(input("Enter number of columns: "))
size = int(input("Enter size of each element: "))
i = int(input("Enter row index: "))
j = int(input("Enter column index: "))

address = base + ((j * rows + i) * size)

print("Effective Address =", address)


//Insertion and Deletion in Array
arr = list(map(int, input("Enter array elements: ").split()))

# Insertion
pos = int(input("Enter insertion position: "))
value = int(input("Enter value: "))

arr.insert(pos, value)
print("After Insertion:", arr)

# Deletion
pos = int(input("Enter deletion position: "))

if 0 <= pos < len(arr):
    arr.pop(pos)
    print("After Deletion:", arr)
else:
    print("Invalid position")


    //Adjacency Matrix and Adjacency List
     n = int(input("Enter number of vertices: "))
e = int(input("Enter number of edges: "))

matrix = [[0] * n for _ in range(n)]
adj_list = [[] for _ in range(n)]

for _ in range(e):
    u, v = map(int, input("Enter edge (u v): ").split())

    matrix[u][v] = 1
    matrix[v][u] = 1

    adj_list[u].append(v)
    adj_list[v].append(u)

print("\nAdjacency Matrix:")
for row in matrix:
    print(row)

print("\nAdjacency List:")
for i in range(n):
    print(i, ":", adj_list[i])


   //BFS
   from collections import deque

n = int(input("Enter number of vertices: "))
e = int(input("Enter number of edges: "))

graph = [[] for _ in range(n)]

for _ in range(e):
    u, v = map(int, input("Enter edge: ").split())
    graph[u].append(v)
    graph[v].append(u)

start = int(input("Enter starting vertex: "))

visited = [False] * n
queue = deque([start])
visited[start] = True

print("BFS Traversal:")

while queue:
    vertex = queue.popleft()
    print(vertex, end=" ")

    for neighbour in graph[vertex]:
        if not visited[neighbour]:
            visited[neighbour] = True
            queue.append(neighbour)


//DFS
n = int(input("Enter number of vertices: "))
e = int(input("Enter number of edges: "))

graph = [[] for _ in range(n)]

for _ in range(e):
    u, v = map(int, input("Enter edge: ").split())
    graph[u].append(v)
    graph[v].append(u)

visited = [False] * n


def dfs(vertex):
    visited[vertex] = True
    print(vertex, end=" ")

    for neighbour in graph[vertex]:
        if not visited[neighbour]:
            dfs(neighbour)


start = int(input("Enter starting vertex: "))

print("DFS Traversal:")
dfs(start)


//Prim's Algorithm
n = int(input("Enter number of vertices: "))

graph = []

print("Enter adjacency matrix:")
for _ in range(n):
    graph.append(list(map(int, input().split())))

selected = [False] * n
selected[0] = True

total_cost = 0

print("Edges in MST:")

for _ in range(n - 1):
    minimum = float('inf')
    x = y = -1

    for i in range(n):
        if selected[i]:
            for j in range(n):
                if not selected[j] and graph[i][j] != 0:
                    if graph[i][j] < minimum:
                        minimum = graph[i][j]
                        x = i
                        y = j

    print(x, "--", y, "=", minimum)
    total_cost += minimum
    selected[y] = True

print("Minimum Cost =", total_cost)


//Kruskal's Algorithm
n = int(input("Enter number of vertices: "))
e = int(input("Enter number of edges: "))

edges = []

for _ in range(e):
    u, v, w = map(int, input("Enter u v weight: ").split())
    edges.append((w, u, v))

edges.sort()

parent = list(range(n))


def find(x):
    if parent[x] != x:
        parent[x] = find(parent[x])
    return parent[x]


def union(a, b):
    a = find(a)
    b = find(b)

    if a != b:
        parent[b] = a
        return True

    return False


total = 0
count = 0

print("Edges in MST:")

for w, u, v in edges:
    if union(u, v):
        print(u, "--", v, "=", w)
        total += w
        count += 1

        if count == n - 1:
            break

print("Minimum Cost =", total)


//Minimum Spanning Tree (MST)
# MST using Prim's Algorithm

n = int(input("Enter number of vertices: "))

graph = []

print("Enter adjacency matrix:")
for _ in range(n):
    graph.append(list(map(int, input().split())))

visited = [False] * n
visited[0] = True

total = 0

print("Minimum Spanning Tree:")

for _ in range(n - 1):
    minimum = float('inf')
    u = v = -1

    for i in range(n):
        if visited[i]:
            for j in range(n):
                if not visited[j] and graph[i][j] != 0:
                    if graph[i][j] < minimum:
                        minimum = graph[i][j]
                        u = i
                        v = j

    print(u, "--", v, "=", minimum)
    total += minimum
    visited[v] = True

print("Total MST Cost =", total)


//Dijkstra's Algorithm
n = int(input("Enter number of vertices: "))

graph = []

print("Enter adjacency matrix:")
for _ in range(n):
    graph.append(list(map(int, input().split())))

source = int(input("Enter source vertex: "))

distance = [float('inf')] * n
visited = [False] * n

distance[source] = 0

for _ in range(n):
    u = -1
    minimum = float('inf')

    for i in range(n):
        if not visited[i] and distance[i] < minimum:
            minimum = distance[i]
            u = i

    if u == -1:
        break

    visited[u] = True

    for v in range(n):
        if graph[u][v] != 0:
            new_distance = distance[u] + graph[u][v]

            if new_distance < distance[v]:
                distance[v] = new_distance

print("Shortest Distances:")

for i in range(n):
    print(source, "to", i, "=", distance[i])


//Bellman-Ford Algorithm
n = int(input("Enter number of vertices: "))
e = int(input("Enter number of edges: "))

edges = []

for _ in range(e):
    u, v, w = map(int, input("Enter u v weight: ").split())
    edges.append((u, v, w))

source = int(input("Enter source vertex: "))

distance = [float('inf')] * n
distance[source] = 0

for _ in range(n - 1):
    for u, v, w in edges:
        if distance[u] != float('inf'):
            if distance[u] + w < distance[v]:
                distance[v] = distance[u] + w

negative_cycle = False

for u, v, w in edges:
    if distance[u] != float('inf') and distance[u] + w < distance[v]:
        negative_cycle = True
        break

if negative_cycle:
    print("Negative weight cycle exists")
else:
    print("Shortest distances:")
    for i in range(n):
        print(source, "to", i, "=", distance[i])


//Fibonacci Series
n = int(input("Enter number of terms: "))

a = 0
b = 1

print("Fibonacci Series:")

for i in range(n):
    print(a, end=" ")
    a, b = b, a + b


    //University Attendance Analysis
   students = {}

n = int(input("Enter number of students: "))

for i in range(n):
    name = input("Enter student name: ")
    attendance = float(input("Enter attendance percentage: "))
    students[name] = attendance

print("\nAttendance Analysis:")

for name, attendance in students.items():
    if attendance >= 75:
        status = "Eligible"
    else:
        status = "Not Eligible"

    print(name, ":", attendance, "% -", status)


//Hospital Emergency Monitoring  
patients = []

n = int(input("Enter number of patients: "))

for i in range(n):
    name = input("Enter patient name: ")
    severity = int(input("Enter severity (1-10): "))

    patients.append((severity, name))

patients.sort(reverse=True)

print("\nEmergency Priority List:")

for severity, name in patients:
    if severity >= 8:
        priority = "Critical"
    elif severity >= 5:
        priority = "Moderate"
    else:
        priority = "Low"

    print(name, "- Severity:", severity, "-", priority)


  //Student Name Search
  students = []

n = int(input("Enter number of students: "))

for i in range(n):
    name = input("Enter student name: ")
    students.append(name)

search_name = input("Enter name to search: ")

if search_name in students:
    print("Student Found")
else:
    print("Student Not Found")


//Library Book Code Validator
import re

code = input("Enter book code: ")

# Format: LIB-1234
pattern = r"^LIB-\d{4}$"

if re.match(pattern, code):
    print("Valid Book Code")
else:
    print("Invalid Book Code")
