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


//Height of a tree
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None


def create_tree():
    data = int(input("Enter node value (-1 for no node): "))

    if data == -1:
        return None

    node = Node(data)

    print("Enter left child of", data)
    node.left = create_tree()

    print("Enter right child of", data)
    node.right = create_tree()

    return node


def height(root):
    if root is None:
        return 0

    left_height = height(root.left)
    right_height = height(root.right)

    return 1 + max(left_height, right_height)


# Main
print("Create Binary Tree")
root = create_tree()

print("Height of the tree =", height(root))

//number of node in a tree
  
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None


def create_tree():
    data = int(input("Enter node value (-1 for no node): "))

    if data == -1:
        return None

    node = Node(data)

    print("Enter left child of", data)
    node.left = create_tree()

    print("Enter right child of", data)
    node.right = create_tree()

    return node


def count_nodes(root):
    if root is None:
        return 0

    return 1 + count_nodes(root.left) + count_nodes(root.right)


# Main
print("Create Binary Tree")
root = create_tree()

print("Number of nodes =", count_nodes(root))

//number of internal node
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None


def create_tree():
    data = int(input("Enter node value (-1 for no node): "))

    if data == -1:
        return None

    node = Node(data)

    print("Enter left child of", data)
    node.left = create_tree()

    print("Enter right child of", data)
    node.right = create_tree()

    return node


def count_internal_nodes(root):
    if root is None:
        return 0

    # Leaf node হলে internal node নয়
    if root.left is None and root.right is None:
        return 0

    return 1 + count_internal_nodes(root.left) + count_internal_nodes(root.right)


# Main
print("Create Binary Tree")
root = create_tree()

print("Number of internal nodes =", count_internal_nodes(root))

//number of leaf node
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None


def create_tree():
    data = int(input("Enter node value (-1 for no node): "))

    if data == -1:
        return None

    node = Node(data)

    print("Enter left child of", data)
    node.left = create_tree()

    print("Enter right child of", data)
    node.right = create_tree()

    return node


def count_leaf_nodes(root):
    if root is None:
        return 0

    # Leaf node: no left child and no right child
    if root.left is None and root.right is None:
        return 1

    return count_leaf_nodes(root.left) + count_leaf_nodes(root.right)


# Main
print("Create Binary Tree")
root = create_tree()

print("Number of leaf nodes =", count_leaf_nodes(root))

//Binary Search
def binary_search(arr, key):
    low = 0
    high = len(arr) - 1

    while low <= high:
        mid = (low + high) // 2

        if arr[mid] == key:
            return mid

        elif arr[mid] < key:
            low = mid + 1

        else:
            high = mid - 1

    return -1


# User input
n = int(input("Enter number of elements: "))

arr = []

for i in range(n):
    value = int(input("Enter element: "))
    arr.append(value)

# Binary search requires sorted array
arr.sort()

print("Sorted array:", arr)

key = int(input("Enter element to search: "))

result = binary_search(arr, key)

if result != -1:
    print("Element found at index", result)
else:
    print("Element not found")

//effective address of a 1d array

# Effective Address of 1D Array

n = int(input("Enter number of elements: "))

arr = []

for i in range(n):
    value = int(input("Enter element: "))
    arr.append(value)

base = int(input("Enter base address: "))
index = int(input("Enter index: "))
size = int(input("Enter size of each element (in bytes): "))

effective_address = base + (index * size)

print("Array:", arr)
print("Effective Address =", effective_address)

//effective address of 2d array column major
# Effective Address of 2D Array - Column Major

rows = int(input("Enter number of rows: "))
cols = int(input("Enter number of columns: "))

arr = []

for i in range(rows):
    row = []
    for j in range(cols):
        value = int(input(f"Enter element [{i}][{j}]: "))
        row.append(value)
    arr.append(row)

base = int(input("Enter base address: "))
i = int(input("Enter row index: "))
j = int(input("Enter column index: "))
size = int(input("Enter size of each element (in bytes): "))

effective_address = base + ((j * rows) + i) * size

print("Effective Address =", effective_address)

//insersion and deletion in an array
# Insertion and Deletion in Array

n = int(input("Enter number of elements: "))

arr = []

for i in range(n):
    value = int(input("Enter element: "))
    arr.append(value)

print("Original array:", arr)

# Insertion
pos = int(input("Enter position for insertion: "))
value = int(input("Enter value to insert: "))

arr.insert(pos, value)

print("Array after insertion:", arr)

# Deletion
pos = int(input("Enter position for deletion: "))

if 0 <= pos < len(arr):
    arr.pop(pos)
    print("Array after deletion:", arr)
else:
    print("Invalid position")

//adjacency matrix
vertices = int(input("Enter number of vertices: "))
edges = int(input("Enter number of edges: "))

matrix = [[0 for _ in range(vertices)] for _ in range(vertices)]

for i in range(edges):
    u = int(input("Enter source vertex: "))
    v = int(input("Enter destination vertex: "))

    matrix[u][v] = 1
    matrix[v][u] = 1

print("\nAdjacency Matrix:")

for row in matrix:
    print(row)

//adjacency list
vertices = int(input("Enter number of vertices: "))
edges = int(input("Enter number of edges: "))

graph = [[] for _ in range(vertices)]

for i in range(edges):
    u = int(input("Enter source vertex: "))
    v = int(input("Enter destination vertex: "))

    graph[u].append(v)
    graph[v].append(u)

print("\nAdjacency List:")

for i in range(vertices):
    print(i, "->", graph[i])

//BFS
from collections import deque

vertices = int(input("Enter number of vertices: "))
edges = int(input("Enter number of edges: "))

graph = [[] for _ in range(vertices)]

for i in range(edges):
    u = int(input("Enter source vertex: "))
    v = int(input("Enter destination vertex: "))

    graph[u].append(v)
    graph[v].append(u)

start = int(input("Enter starting vertex: "))

visited = [False] * vertices
queue = deque()

visited[start] = True
queue.append(start)

print("BFS Traversal:", end=" ")

while queue:
    vertex = queue.popleft()
    print(vertex, end=" ")

    for neighbor in graph[vertex]:
        if not visited[neighbor]:
            visited[neighbor] = True
            queue.append(neighbor)

//DFS
vertices = int(input("Enter number of vertices: "))
edges = int(input("Enter number of edges: "))

graph = [[] for _ in range(vertices)]

for i in range(edges):
    u = int(input("Enter source vertex: "))
    v = int(input("Enter destination vertex: "))

    graph[u].append(v)
    graph[v].append(u)


visited = [False] * vertices


def dfs(vertex):
    visited[vertex] = True
    print(vertex, end=" ")

    for neighbor in graph[vertex]:
        if not visited[neighbor]:
            dfs(neighbor)


start = int(input("Enter starting vertex: "))

print("DFS Traversal:", end=" ")
dfs(start)

//PRIMS ALGO
vertices = int(input("Enter number of vertices: "))
edges = int(input("Enter number of edges: "))

graph = [[] for _ in range(vertices)]

for i in range(edges):
    u = int(input("Enter source vertex: "))
    v = int(input("Enter destination vertex: "))
    w = int(input("Enter weight: "))

    graph[u].append((v, w))
    graph[v].append((u, w))


visited = [False] * vertices
total_cost = 0

# Start from vertex 0
visited[0] = True

print("\nEdges in Minimum Spanning Tree:")

for _ in range(vertices - 1):

    minimum = float('inf')
    selected_u = -1
    selected_v = -1

    for u in range(vertices):
        if visited[u]:
            for v, weight in graph[u]:
                if not visited[v] and weight < minimum:
                    minimum = weight
                    selected_u = u
                    selected_v = v

    if selected_v == -1:
        break

    print(selected_u, "--", selected_v, "=", minimum)

    total_cost += minimum
    visited[selected_v] = True


print("Minimum Cost =", total_cost)

//Kruskal algo
vertices = int(input("Enter number of vertices: "))
edges = int(input("Enter number of edges: "))

edge_list = []

for i in range(edges):
    u = int(input("Enter source vertex: "))
    v = int(input("Enter destination vertex: "))
    w = int(input("Enter weight: "))

    edge_list.append((w, u, v))


# Sort edges by weight
edge_list.sort()

parent = list(range(vertices))


def find(x):
    if parent[x] != x:
        parent[x] = find(parent[x])
    return parent[x]


def union(a, b):
    root_a = find(a)
    root_b = find(b)

    if root_a != root_b:
        parent[root_b] = root_a
        return True

    return False


total_cost = 0
count = 0

print("\nEdges in Minimum Spanning Tree:")

for weight, u, v in edge_list:

    if union(u, v):
        print(u, "--", v, "=", weight)
        total_cost += weight
        count += 1

        if count == vertices - 1:
            break


print("Minimum Cost =", total_cost)

//Dijkstra algo
vertices = int(input("Enter number of vertices: "))
edges = int(input("Enter number of edges: "))

graph = [[] for _ in range(vertices)]

for i in range(edges):
    u = int(input("Enter source vertex: "))
    v = int(input("Enter destination vertex: "))
    weight = int(input("Enter weight: "))

    graph[u].append((v, weight))
    graph[v].append((u, weight))


source = int(input("Enter source vertex: "))

distance = [float('inf')] * vertices
visited = [False] * vertices

distance[source] = 0

for _ in range(vertices):

    min_distance = float('inf')
    current = -1

    # Find unvisited vertex with minimum distance
    for i in range(vertices):
        if not visited[i] and distance[i] < min_distance:
            min_distance = distance[i]
            current = i

    if current == -1:
        break

    visited[current] = True

    # Update neighbouring vertices
    for neighbor, weight in graph[current]:

        new_distance = distance[current] + weight

        if new_distance < distance[neighbor]:
            distance[neighbor] = new_distance


print("\nShortest distances from vertex", source)

for i in range(vertices):
    print("Vertex", i, "=", distance[i])

//Bellman ford
vertices = int(input("Enter number of vertices: "))
edges = int(input("Enter number of edges: "))

edge_list = []

for i in range(edges):
    u = int(input("Enter source vertex: "))
    v = int(input("Enter destination vertex: "))
    weight = int(input("Enter weight: "))

    edge_list.append((u, v, weight))

source = int(input("Enter source vertex: "))

distance = [float('inf')] * vertices
distance[source] = 0

# Relax all edges V-1 times
for i in range(vertices - 1):

    for u, v, weight in edge_list:

        if distance[u] != float('inf') and \
           distance[u] + weight < distance[v]:

            distance[v] = distance[u] + weight


# Check for negative weight cycle
negative_cycle = False

for u, v, weight in edge_list:

    if distance[u] != float('inf') and \
       distance[u] + weight < distance[v]:

        negative_cycle = True
        break


if negative_cycle:
    print("Negative weight cycle exists")

else:
    print("\nShortest distances from vertex", source)

    for i in range(vertices):
        print("Vertex", i, "=", distance[i])

//fibonacci series
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

pattern = r"^LIB-\d{4}$"

if re.match(pattern, code):
    print("Valid Book Code")
else:
    print("Invalid Book Code")
