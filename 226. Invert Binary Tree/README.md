### 내풀이
``` cpp
class Solution {
public:
    TreeNode* invertTree(TreeNode* root) {
        invertTreeCall(root);
        return root;
    }
    void invertTreeCall(TreeNode* node){
        if(node == nullptr || (node->left == nullptr && node->right == nullptr))
            return;
        swap(node->left,node->right);
        invertTreeCall(node->left);
        invertTreeCall(node->right);
            
    }
};
```

Time Complexity O(n)    
Space : O(1)

good ! 
