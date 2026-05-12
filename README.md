# Weekly Coding #5: Skyrail Station Navigator

## Summary

This program works with binary trees and binary search trees (BST). It performs tree traversals such as preorder, inorder, and postorder to visit nodes in different ways. It also supports BST operations like searching for a value and inserting a new value into the correct position. These functions help organize data efficiently and allow faster searching compared to normal lists.

The traversal functions use recursion to move through the tree structure. The BST functions take advantage of the BST property, where smaller values are stored on the left side and larger values are stored on the right side. This makes searching and inserting more efficient.

---

## Approach

### `preorder_values`
- Visit the current node first.
- Recursively visit the left subtree.
- Recursively visit the right subtree.
- Store visited values in a list.

### `inorder_values`
- Recursively visit the left subtree first.
- Visit the current node.
- Recursively visit the right subtree.
- This traversal returns sorted values for a BST.

### `postorder_values`
- Recursively visit the left subtree.
- Recursively visit the right subtree.
- Visit the current node last.
- Useful when child nodes must be processed before the parent.

### `bst_contains`
- Compare the target value with the current node.
- If equal, return `True`.
- If smaller, search the left subtree.
- If larger, search the right subtree.
- Return `False` if the value is not found.

### `bst_insert`
- Compare the new value with the current node.
- Insert into the left subtree if smaller.
- Insert into the right subtree if larger.
- Create a new node if the correct position is empty.
- Ignore duplicate values.

---

## Complexity

### `preorder_values`
- **Time:** `O(n)`
- **Space:** `O(h)`
- **Why:** Every node is visited once, and recursion stack depth depends on the height of the tree.

### `inorder_values`
- **Time:** `O(n)`
- **Space:** `O(h)`
- **Why:** Each node is visited once, and recursion depth depends on the tree height.

### `postorder_values`
- **Time:** `O(n)`
- **Space:** `O(h)`
- **Why:** Traverses every node once with recursive calls based on height.

### `bst_contains`
- **Time:** `O(h)`
- **Space:** `O(h)`
- **Why:** Only one path from root to leaf is followed during the search.

### `bst_insert`
- **Time:** `O(h)`
- **Space:** `O(h)`
- **Why:** The function follows one path to insert the value, and recursion depth depends on tree height.

---

## Edge-Case Checklist

- [x] Empty tree traversal returns `[]`
  - Functions return an empty list when the root is `None`.

- [x] Single-node traversal works correctly
  - Traversal functions return a list containing only that node’s value.

- [x] `bst_contains` returns `False` for an empty tree
  - The function immediately returns `False` if the tree is empty.

- [x] `bst_contains` returns `False` when the target value is missing
  - Recursion eventually reaches a `None` node and returns `False`.

- [x] `bst_insert` creates a root when the tree is empty
  - A new node is created when inserting into an empty tree.

- [x] `bst_insert` ignores duplicate values
  - Duplicate values are not inserted into the BST.

- [x] Tested deeper insert cases
  - Inserted values such as `25` and `55` to confirm correct placement.

---

## Assistance & Sources

### AI used? (Y/N)
- Y

### What AI helped with
- Understanding recursion and traversal order.
- Verifying BST insertion and search logic.
- Improving explanations for complexity and edge cases.

### Other sources used
- Class notes
- Lecture slides
- Python documentation
