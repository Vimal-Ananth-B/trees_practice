94\. Binary Tree Inorder Traversal

Solved

Easy

Topics

Given the root of a binary tree, return the inorder traversal of its nodes' values.



Example 1:



Input: root = \[1,null,2,3]

Output: \[1,3,2]



Example 2:



Input: root = \[1,2,3,4,5,null,8,null,null,6,7,9]

Output: \[4,2,6,5,7,1,3,9,8]



Example 3:



Input: root = \[]

Output: \[]



Example 4:



Input: root = \[1]

Output: \[1]



&nbsp;



Constraints:



The number of nodes in the tree is in the range \[0, 100].

-100 <= Node.val <= 100



/\*\*

&nbsp;\* Definition for a binary tree node.

&nbsp;\* public class TreeNode {

&nbsp;\*     int val;

&nbsp;\*     TreeNode left;

&nbsp;\*     TreeNode right;

&nbsp;\*     TreeNode() {}

&nbsp;\*     TreeNode(int val) { this.val = val; }

&nbsp;\*     TreeNode(int val, TreeNode left, TreeNode right) {

&nbsp;\*         this.val = val;

&nbsp;\*         this.left = left;

&nbsp;\*         this.right = right;

&nbsp;\*     }

&nbsp;\* }

&nbsp;\*/





**Answer:**

**Recursive way:**



class Solution {

&nbsp;   public List<Integer> inorderTraversal(TreeNode root) {

&nbsp;      List<Integer> res=new ArrayList<>();

&nbsp;       inorder(root,res);

&nbsp;       return res;

&nbsp;   }

&nbsp;   private void inorder(TreeNode node,List<Integer> res)

&nbsp;   {

&nbsp;       if(node==null){

&nbsp;           return;

&nbsp;       }

&nbsp;       inorder(node.left,res);

&nbsp;       res.add(node.val);

&nbsp;       inorder(node.right,res);

&nbsp;   }

}



**Iterative way:**



class Solution {

&nbsp;   public List<Integer> inorderTraversal(TreeNode root) {

&nbsp;      TreeNode current=root;

&nbsp;      List<Integer> listt=new ArrayList<>();

&nbsp;      Stack<TreeNode> stackk=new Stack<>();

&nbsp;      while(current!=null || !stackk.isEmpty())

&nbsp;      {

&nbsp;      if(current!=null)

&nbsp;      {

&nbsp;       stackk.push(current);

&nbsp;       current=current.left;

&nbsp;      }

&nbsp;      else

&nbsp;      {

&nbsp;       current=stackk.pop();

&nbsp;       listt.add(current.val);

&nbsp;       current=current.right;

&nbsp;      }

&nbsp;      }

&nbsp;      return listt;

&nbsp;   }

}

