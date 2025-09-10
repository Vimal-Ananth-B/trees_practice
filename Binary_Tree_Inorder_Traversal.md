Leetcode94. Binary Tree Inorder Traversal
Given the root of a binary tree, return the inorder traversal of its nodes' values.

Example 1:

Input: root = [1,null,2,3]
Output: [1,3,2]

Example 2:

Input: root = [1,2,3,4,5,null,8,null,null,6,7,9]
Output: [4,2,6,5,7,1,3,9,8]

Example 3:

Input: root = []
Output: []

Example 4:

Input: root = [1]
Output: [1]

 

Constraints:

The number of nodes in the tree is in the range [0, 100].
-100 <= Node.val <= 100

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


Answer:
Recursive way:

class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
       List<Integer> res=new ArrayList<>();
        inorder(root,res);
        return res;
    }
    private void inorder(TreeNode node,List<Integer> res)
    {
        if(node==null){
            return;
        }
        inorder(node.left,res);
        res.add(node.val);
        inorder(node.right,res);
    }
}

Iterative way:

class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
       TreeNode current=root;
       List<Integer> listt=new ArrayList<>();
       Stack<TreeNode> stackk=new Stack<>();
       while(current!=null || !stackk.isEmpty())
       {
       if(current!=null)
       {
        stackk.push(current);
        current=current.left;
       }
       else
       {
        current=stackk.pop();
        listt.add(current.val);
        current=current.right;
       }
       }
       return listt;
    }
}



