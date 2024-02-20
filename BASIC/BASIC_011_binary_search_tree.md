	After the boy returned home and thought about what he had previously learned about linked lists from his teacher, he realised that linked lists are very powerful data structures. Still, he discovered the shortcomings of chained tables as a data structure. So, for the third week, he returned to the study where his teacher was and began his third week of study.

## Binary tree

TEACHER: "Firstly, do you know what a binary tree is?"

YOUTH: "Maybe a little bit. It's a data structure, right? I have Googled it, and it says every binary tree has a node, and each node has two children at most. "

TEACHER: "You're right, but if we set a rule with a binary tree. It will cause exciting things."

YOUTH: "A rule?"

## Binary search tree and the rules

TEACHER:  "Let's go back to the basic rules of the binary search tree: the left subtree of each node contains only values less than that node, and the right subtree contains only values greater than that node. What does this make you think of?"

YOUTH: "This data structure not only stores the data, it also seems to sort the data, which is a little interesting. Maybe this data structure."

### Analogy


## The benefit of binary search tree

YOUTH: "Based on the basics of this BST, we may be able to find the value we want quickly because the number of searches we need to 
Perform each time is cut in half."

## The reasoning process of BST implement

TEACHER: "Yes, exactly. What if we want to implement a simple BST in Python? What would we need first? Firstly, tell me what the ==unknown== is. Answer me in your words."

YOUTH: "You mean we want to write a BST in Python? And the BST is a data structure, so the unknown is to write a BST data structure that allows for searching, deleting, and adding data."

TEACHER: "And traverse data. OK, please tell me the condition or the ==known==?"

YOUTH: "We know each node has value and has two children at most, and the left sub-tree is less than the node, and the right sub-tree is greater than the node."

TEACHER: "Great. Can you use a picture to show what a binary search tree is?"
213
YOUTH: "If we have a list of numbers like 1,3, 4,6,7,8,10,13,14. The binary search tree may be like this: ![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202402192307547.png)

"
YOUTH: "I find some interesting things when I draw the picture. Firstly, the root is very important, we have to choose the middle number of the number list. Second, the left and right subtrees are also a binary search tree. All subtree can be used both as subtrees and as root for the next subtree."

