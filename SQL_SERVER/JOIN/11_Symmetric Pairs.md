# Problem

You are given a table, Functions, containing two columns: X and Y.

![](https://s3.amazonaws.com/hr-challenge-images/12892/1443818798-51909e977d-1.png)

Two pairs (X1, Y1) and (X2, Y2) are said to be symmetric pairs if X1 = Y2 and X2 = Y1.

Write a query to output all such symmetric pairs in ascending order by the value of X.

**Sample Input**

![](https://s3.amazonaws.com/hr-challenge-images/12892/1443818693-b384c24e35-2.png)

**Sample Output**

    20 20
    20 21
    22 23

## CODE:

    SELECT f1.X, f1.Y FROM Functions f1
    INNER JOIN Functions f2 ON f1.X=f2.Y AND f1.Y=f2.X
    GROUP BY f1.X, f1.Y
    HAVING COUNT(f1.X)>1 or f1.X<f1.Y
    ORDER BY f1.X;
    
## Output:
Your Output (stdout)

    2 24 
    4 22 
    5 21 
    6 20 
    8 18 
    9 17 
    11 15 
    13 13 

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**
