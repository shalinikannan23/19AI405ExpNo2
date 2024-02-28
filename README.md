# EX-02 Implement Depth First Search Traversal of a Graph
### Aim:
To Implement Depth First Search Traversal of a Graph using Python 3.
### Theory:
Depth First Traversal(or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. 
Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.
<table>
<tr>
<td>

Step 1: Initially, stack and visited arrays are empty.
Queue and visited arrays are empty initi ally.
Stack and visited arrays are empty initially.
</td> 
<td>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/640b3c6f-3ac1-49a2-a955-68da9a71f446) 
</td>
</tr> 
<tr>
<td>

Step 2: Visit 0 and put its adjacent nodes which are not visited yet into the stack.
 Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack
 Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack
</td> 
<td>

 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/86dcf7d9-1f9d-49b0-a821-5976a6e77606)
</td>
</tr> 
<tr>
<td>

Step 3: Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
Visit node 1
 Visit node 1

</td> 
<td>

 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/e6017942-08b1-4742-87ad-c97eb97bf985)
</td>
</tr> 
<tr>
<td>

Step 4: Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack.
 Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack
 Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack
</td> 
<td>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/6e6d123c-60ae-4f9c-a27c-c4fc7e57d57c)
</td>
</tr> 
<tr>
<td>

Step 5: Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
 Visit node 4
 Visit node 4
</td> 
<td>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/20b76a05-5668-4da5-8189-e10fb1bb7238)
</td>
</tr> 
<tr>
<td>

Step 6: Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
Visit node 3
Visit node 3
Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.
</td> 
<td>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/3b88f04a-7846-4f75-89b4-22bbd5b48e52)
</td>
</tr> 
</table>

### Algorithm:
 Step-1: Construct a Graph with Nodes and Edges.<br>
 Step-2: Depth First Search Uses Stack and Recursion.<br>
 Step-3: Insert a START node to the STACK.<br>
 Step-4: Find its Successors Or neighbors and Check whether the node is visited or not.<br>
 Step-5: If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.

### Program:
```Python
DEVELOPED BY : SHALINI K
REGISTER NUMBER: 212222240095
#import defaultdict
from collections import defaultdict
def dfs(graph,start,visited,path):
    path.append(start)
    visited[start]=True
    for neighbour in graph[start]:
        if visited[neighbour]==False:
            dfs(graph,neighbour,visited,path)
            visited[neighbour]=True
    return path
graph=defaultdict(list)
n,e=map(int,input().split())
for i in range(e):
    u,v=map(str,input().split())
    graph[u].append(v)
    graph[v].append(u)
#print(graph)
start='A'
visited=defaultdict(bool)
path=[]
traversedpath=dfs(graph,start,visited,path)
print(traversedpath)
```
### Execution:
<table border=3>
<tr border=3>
<td border=3>
 
**Input:** <br>
8 9<br>
A B<br>
A C<br>
B D<br>
B E<br>
C D<br>
C G<br>
D F<br>
F G<br>
F H<br>
</td> 
<td valign=top>

**Output:** <br>
['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']
 
</td>
</tr> 
</table>


### Result:
Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.

