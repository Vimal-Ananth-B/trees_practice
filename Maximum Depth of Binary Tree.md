Leetcode 104. Maximum Depth of Binary Tree



Given the root of a binary tree, return its maximum depth.



A binary tree's maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.



Example 1:



Input: root = \[3,9,20,null,null,15,7]

Output: 3

Example 2:



Input: root = \[1,null,2]

Output: 2



```

\# Iterative method 



class Solution {

&nbsp;   static class DepthNode

&nbsp;   {

&nbsp;       TreeNode current;

&nbsp;       int depth;

&nbsp;       DepthNode(TreeNode current,int depth)

&nbsp;       {

&nbsp;           this.current=current;

&nbsp;           this.depth=depth;

&nbsp;       }

&nbsp;   }

&nbsp;   public int maxDepth(TreeNode root) {

&nbsp;       if (root==null) 

&nbsp;       {

&nbsp;           return 0;

&nbsp;       } 

&nbsp;     Stack<DepthNode> stack=new Stack<>();

&nbsp;     stack.push(new DepthNode(root,1));

&nbsp;       int maxDepth=0;

&nbsp;     while(!stack.isEmpty())

&nbsp;     {

&nbsp;       DepthNode dp=stack.pop();

&nbsp;       TreeNode currentNode=dp.current;

&nbsp;       int depth=dp.depth;

&nbsp;       maxDepth=Math.max(depth,maxDepth);

&nbsp;       if(currentNode.left!=null)

&nbsp;       {

&nbsp;           stack.push(new DepthNode(currentNode.left,1+depth));

&nbsp;       }

&nbsp;       if(currentNode.right!=null)

&nbsp;       {

&nbsp;           stack.push(new DepthNode(currentNode.right,1+depth));

&nbsp;       }

&nbsp;     }

&nbsp;     return maxDepth;

&nbsp;   }

}



\# **Recursive method**



class Solution {

&nbsp;public int maxDepth(TreeNode root) {

&nbsp;       return (root==null) ? 0 : 1 + Math.max(maxDepth(root.left),maxDepth(root.right));

}

}

