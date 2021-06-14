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
	
	
4. SuffixTrie


class SuffixTrie:
    def __init__(self, string):
        self.root = {}
        self.endSymbol = "*"
        self.populateSuffixTrieFrom(string)

   def populateSuffixTrieFrom(self, string):
        # Write your code here.
        for i in range(len(string)):
			self.insertSubstringStartingAt(i, string)
			
def insertSubstringStartingAt(self, i , string):
		node = self.root
		for j in range(i,len(string)):
			letter = string[j]
			if letter not in node:
				node[letter] = {}
			node = node[letter]
		node[self.endSymbol] = True

  def contains(self, string):
        # Write your code here.
        node = self.root
		for j in range(len(string)):
			letter = string[j]
			if letter not in node:
				return False
			node = node[letter]
		return self.endSymbol in node

5. Node Depths

def nodeDepths(root, depth=0):
    # Write your code here.
    if root is None:
		return 0
	return depth + nodeDepths(root.left, depth+1) + nodeDepths(root.right, depth+1)
	


# This is the class of the input binary tree.
class BinaryTree:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None
	
6. Sorted Squared Array

def sortedSquaredArray(array):
    # Write your code here.
	sortedArray = []
    for val in array:
		sortedArray.append(val * val)
	sortedArray.sort()
	return sortedArray


7. FindThree Largest Numbers
