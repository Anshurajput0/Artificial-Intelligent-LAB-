# Artificial-Intelligent-LAB-
graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['E', 'F'],
    'D': ['G', 'B'],
    'E': ['B', 'C'],
    'F': ['C', 'H'],
    'G': ['I'],
    'I':['J'],
    'J':[],
    'H': ['K'],
    'K': ['L'],
    'L': ['M'],
    'M': ['N'],
    'N':[]
}
lable={
       'A':[0,0],
       'B':[0,3],
       'C':[4,0],
       'D':[3,0],
       'E':[4,3],
       'F':[1,3],
       'G':[3,3],
       'H':[1,0],
       'I':[4,2],
       'J':[0,2],
       'K':[0,1],
       'L':[4,1],
       'M':[2,3],
       'N':[2,0],
       }

visited = []
stack = []
res = ['J', 'N']


def dfs(visited, graph, node):
    visited.append(node)
    stack.append(node)
    while stack:
        s = stack.pop(0)
        if s in res:
            print(s, 'Reached')
            
            break
        print(s, end=' ')
        print(lable[s])
        for neighbour in graph[s]:
            if neighbour not in visited:
                visited.append(neighbour)
                stack.append(neighbour)


dfs(visited,graph,'A')
