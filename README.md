# BFS
Repository of all Breadth-First Search (BFS) Algorithms
/// Finding the maximum depth of a N-ary tree

/*
// Definition for a Node.
class Node {
    public int val;
    public List<Node> children;

    public Node() {}

    public Node(int _val) {
        val = _val;
    }

    public Node(int _val, List<Node> _children) {
        val = _val;
        children = _children;
    }
};
*/

class Solution {
    public int maxDepth(Node root) {
        /// Using breadth first search
        if (root == null)
            return 0;
        int depth = 0;
        Queue used as a common BFS Data Structure
        Queue<Node> queue = new LinkedList<Node>();
        queue.offer(root);
        
        while (!queue.isEmpty()) {
            int size = queue.size();
            
            for (int i=0;i<size;i++) {
                /// Grabbing the first added node 
                Node current = queue.poll();
                /// Adding the children of the nodes already in the queue, to the queue
                
                for (Node child:current.children) {
                    queue.offer(child);
                }
            }
            /// Incrementing depth for each iteration, as all nodes of the same level are added with each iteration 
            depth++;
        }
        return depth;
    }
}
