## top K Buzzwords problem
1. use hashmap to record the count of the buzzwords, O(KN)
2. use heapify the N Buzzwords and, loop through the list of strings O(Nlog(k)

## Inorder traversal
### iterasive
while(root or stack):
while(root):
stack.append(root)
root = root.left
l = stack.pop()
root = l.right

### recursive
def inorder(root):
if root == none:
return
inorder(root.left)
root.val
inorder(root.right)

## preorder traversal
### recursive
def preorder(root):
if root == none:
return
root.val
preorder(root.left)
preorder(root.right)

## Postorder traversal
### recursive
def postorder(root):
if root == none:
return
postorder(root.left)
postorder(root.right)
root.val
