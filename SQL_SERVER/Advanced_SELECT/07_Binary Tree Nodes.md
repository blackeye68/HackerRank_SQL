## Problem

You are given a table, BST, containing two columns: N and P, where N represents the value of a node in Binary Tree, and P is the parent of N.

![](https://s3.amazonaws.com/hr-challenge-images/12888/1443818507-5095ab9853-1.png)

Write a query to find the node type of Binary Tree ordered by the value of the node. Output one of the following for each node:

* Root: If node is root node.
* Leaf: If node is leaf node.
* Inner: If node is neither root nor leaf node.

**Sample Input**

![](https://s3.amazonaws.com/hr-challenge-images/12888/1443818467-30644673f6-2.png)

**Sample Output**

    1 Leaf
    2 Inner
    3 Leaf
    5 Root
    6 Leaf
    8 Inner
    9 Leaf
    
**Explanation**

The Binary Tree below illustrates the sample:

![](https://s3.amazonaws.com/hr-challenge-images/12888/1443773633-f9e6fd314e-simply_sql_bst.png)
    
## CODE:

    SELECT N,
    CASE
    WHEN P IS NULL THEN 'Root'
    WHEN N IN (SELECT P FROM BST) THEN 'Inner'
    ELSE 'Leaf'
    END
    FROM BST
    ORDER by N;
    
## Output:
Your Output (stdout)

    1 Leaf 
    2 Inner 
    3 Leaf 
    4 Inner 
    5 Leaf 
    6 Inner 
    7 Leaf 
    8 Leaf 
    9 Inner 
    10 Leaf 
    11 Inner 
    12 Leaf 
    13 Inner 
    14 Leaf 
    15 Root 

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**

