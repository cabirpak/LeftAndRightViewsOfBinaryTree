#include <iostream>
#include <list>
using namespace std;

class Node{
public:
    int data;
    Node* left,* right;
    
    Node(int data):data(data), left(nullptr), right(nullptr){
        
    }
};

class Tree{
    //Node root;
    int maxLevel;
    
public:
    Tree(): maxLevel(0){
        
    }
    
    void reinitialize(){
        maxLevel = 0;
    }
    
    void leftView(Node* root, int level, list<int>& result){
        if(root == nullptr){
            return;
        }
        if(maxLevel < level){
            maxLevel = level;
            //cout << root->data << " ";
            result.push_front(root->data);
        }
        leftView(root->left, level+1, result);
        leftView(root->right, level+1, result);
    }
    
    void rightView(Node* root, int level, list<int>& result){
        if(root == nullptr){
            return;
        }
        if(maxLevel < level){
            maxLevel = level;
            //cout << root->data << " ";
            result.push_back(root->data);
        }
        rightView(root->right, level+1, result);
        rightView(root->left, level+1, result);
    }
};

int main()
{
    Node* root = new Node(1);
    root->left = new Node(2);
    root->right = new Node(3);
    root->right->right = new Node(6);
    
    Tree* tree = new Tree();
    list<int> result;
    tree->leftView(root, 1, result);
    
    result.pop_back();//for not printing the root twice
    
    tree->reinitialize();
    tree->rightView(root, 1, result);
    
    for(auto i=result.begin(); i!=result.end(); i++)
        cout << *i << " ";

    return 0;
}
