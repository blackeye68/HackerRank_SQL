## Problem

Write a query identifying the type of each record in the **TRIANGLES** table using its three side lengths. Output one of the following statements for each record in the table:

* **Equilateral**: It's a triangle with  sides of equal length.
* **Isosceles**: It's a triangle with  sides of equal length.
* **Scalene**: It's a triangle with  sides of differing lengths.
* **Not A Triangle**: The given values of A, B, and C don't form a triangle.

**Input Format**

The **TRIANGLES** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/12887/1443815629-ac2a843fb7-1.png)

Each row in the table denotes the lengths of each of a triangle's three sides.

**Sample Input**

![](https://s3.amazonaws.com/hr-challenge-images/12887/1443815827-cbfc1ca12b-2.png)

**Sample Output**

    Isosceles
    Equilateral
    Scalene
    Not A Triangle
    
**Explanation**

Values in the tuple **_(20,20,23)_** form an Isosceles triangle, because **_A=B_** (3 dấu bằng). 
Values in the tuple **_(20,20)_** form an Equilateral triangle, because **_A=B=C_** (3 dấu bằng) . Values in the tuple **_(20,21,22)_**  form a Scalene triangle, because **_A#B#C_** (dấu không bằng) . 
Values in the tuple **_(13,14,30)_** cannot form a triangle because the combined value of sides **_A_** and **_B_** is not larger than that of side **_C_**.
    
## CODE:

    SELECT
    CASE
    WHEN a=b AND b=c THEN "Equilateral"
    WHEN (a=b or b=c or a=c) AND a+b>c THEN "Isosceles"
    WHEN a!=b AND b!=c AND a+b>c THEN "Scalene"
    ELSE "Not A Triangle"
    END
    FROM TRIANGLES;
    
## Output:
Your Output (stdout)

    Equilateral 
    Equilateral 
    Isosceles 
    Equilateral 
    Isosceles 
    Equilateral 
    Scalene 
    Not A Triangle 
    Scalene 
    Scalene 
    Scalene 
    Not A Triangle 
    Not A Triangle 
    Scalene 
    Equilateral 

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**

