# AlgoexpertSolutions

1. BFS Medium Problem:


class Node:
    def __init__(self, name):
        self.children = []
        self.name = name

    def addChild(self, name):
        self.children.append(Node(name))
        return self

    def breadthFirstSearch(self, array):
        # Write your code here.
		queue = [self]
		while len(queue) > 0:
			current = queue.pop(0)
			array.append(current.name)
			for child in current.children:
				queue.append(child)
    return array
    
    
    2. findClosestValueInBst
    
    def findClosestValueInBst(tree, target):
    # Write your code here.
    return findClosestValueInBstHelper(tree, target, float('inf'))
def findClosestValueInBstHelper(tree, target, closet):
	if tree is None:
		return closet
	if abs(target - closet) > abs(target - tree.value):
		closet = tree.value
	if target < tree.value:
		return findClosestValueInBstHelper(tree.left, target, closet)
	elif target > tree.value:
		return findClosestValueInBstHelper(tree.right, target, closet)
	else:
		return closet
		
		
		



3. Validate Subsequence
    def isValidSubsequence(array, sequence):
    # Write your code here.
	seqIndx = 0
	arrayIndx = 0
	while seqIndx < len(sequence) and arrayIndx < len(array):
		if sequence[seqIndx] == array[arrayIndx]:
			seqIndx += 1
		arrayIndx += 1
	return seqIndx == len(sequence)
