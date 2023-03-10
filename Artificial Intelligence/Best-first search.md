
```python
def best_first_search(problem, f):
	node: Node = problem.INITIAL  # setting starting node
	frontier: list[Node] = [] # priority queue
	reached: dict = {problem.INITIAL: node}

	while len(frontier) != 0:
		node = frontier.pop()
		
		# if current node is a goal, return
		if node in problem.goals:
			return node
			
		for child: Node in problem.expand(node):
			s = child
			if s not in reached or or child.path_cost < reached[s]
```

to be continued