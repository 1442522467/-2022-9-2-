#  剑指 Offer II 047. 二叉树剪枝
给定一个二叉树 根节点 root ，树的每个节点的值要么是 0，要么是 1。请剪除该二叉树中所有节点的值为 0 的子树。

节点 node 的子树为 node 本身，以及所有 node 的后代。
~~~
/**

* Definition for a binary tree node.

* public class TreeNode {

* int val;

* TreeNode left;

* TreeNode right;

* TreeNode() {}

* TreeNode(int val) { this.val = val; }

* TreeNode(int val, TreeNode left, TreeNode right) {

* this.val = val;

* this.left = left;

* this.right = right;

* }

* }

*/

class  Solution {

public  TreeNode  pruneTree(TreeNode  root) {

if(countTree(root)==0){return  null;}

root.left=pruneTree(root.left);

root.right=pruneTree(root.right);

return root;

  

}

  

public  int  countTree(TreeNode  node){

if(node==null){return  0;}

  

int  leftConut=countTree(node.left);

int  rightCount=countTree(node.right);

return leftConut+rightCount+node.val;

}

}
~~~
