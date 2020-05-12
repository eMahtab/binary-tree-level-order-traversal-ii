# Binary Tree Level Order Traversal II
## https://leetcode.com/problems/binary-tree-level-order-traversal-ii


# Implementation :
```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public List<List<Integer>> levelOrderBottom(TreeNode root) {
        List<List<Integer>> res = new ArrayList<>();
        if(root == null)
           return res;
        Queue<TreeNode> q = new LinkedList<>();
        q.offer(root);
        while(!q.isEmpty()) {
            int size = q.size();
            List<Integer> level = new ArrayList<>();
            for(int i = 1; i <= size; i++) {
                TreeNode current = q.poll();
                level.add(current.val);
                if(current.left != null)
                    q.offer(current.left);
                if(current.right != null)
                    q.offer(current.right);
            }
            res.add(level);
        }
        Collections.reverse(res);
        return res;
    }
}
```
