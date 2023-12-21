#bst

First step is to find the node.

There are three conditions once target node is reached-
1. If node has no subtrees then return null.
2. If one of the subtree is null then return the other subtree.
3. If both subtrees are present then-
	1. Find the minimum node in right subtree.
	2. Set the target node value to minimum value.
	3. Delete the node with minimum value in right subtree.


```java
public TreeNode deleteNode(TreeNode root, int target) {
	if (root == null) {
		return null;
	}
	else if (root.val > key) {
		root.left = deleteNode(root.left, key);
	}
	else if (root.val < key) {
		root.right  = deleteNode(root.right, key);
	}
	else {
		TreeNode min = findMin(root.right);
		node.val = min.val;
		root.right = deleteNode(root.right, min.val);
	}
}

private TreeNode findMin(TreeNode node) {
	while (node.left != null) {
		node = node.left;
	}
	return node;
}
```
