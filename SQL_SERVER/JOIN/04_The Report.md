## Problem

You are given two tables: Students and Grades. Students contains three columns ID, Name and Marks.

![](https://s3.amazonaws.com/hr-challenge-images/12891/1443818166-a5c852caa0-1.png)

Grades contains the following data:

![](https://s3.amazonaws.com/hr-challenge-images/12891/1443818137-69b76d805c-2.png)

Ketty gives Eve a task to generate a report containing three columns: Name, Grade and Mark. Ketty doesn't want the NAMES of those students who received a grade lower than 8. The report must be in descending order by grade -- i.e. higher grades are entered first. If there is more than one student with the same grade (8-10) assigned to them, order those particular students by their name alphabetically. Finally, if the grade is lower than 8, use "NULL" as their name and list them by their grades in descending order. If there is more than one student with the same grade (1-7) assigned to them, order those particular students by their marks in ascending order.

Write a query to help Eve.

**Sample Input**

![](https://s3.amazonaws.com/hr-challenge-images/12891/1443818093-b79f376ec1-3.png)

**Sample Output**

    Maria 10 99
    Jane 9 81
    Julia 9 88 
    Scarlet 8 78
    NULL 7 63
    NULL 7 68

**Note**

Print "NULL"  as the name if the grade is less than 8.

**Explanation**

Consider the following table with the grades assigned to the students:

![](https://s3.amazonaws.com/hr-challenge-images/12891/1443818026-0b3af8db30-4.png)

So, the following students got 8, 9 or 10 grades:

* Maria (grade 10)
* Jane (grade 9)
* Julia (grade 9)
* Scarlet (grade 8)

## CODE:

    SELECT CASE 
      WHEN G.Grade<8 THEN NULL ELSE S.Name END AS Name, G.Grade, S.Marks 
    FROM Students S INNER JOIN Grades G ON S.Marks 
      BETWEEN G.Min_Mark and G.Max_Mark 
    ORDER BY G.Grade DESC,Name,Marks;
    
## Output:
Your Output (stdout)

    Britney 10 95 
    Heraldo 10 94 
    Julia 10 96 
    Kristeen 10 100 
    Stuart 10 99 
    Amina 9 89 
    Christene 9 88 
    Salma 9 81 
    Samantha 9 87 
    Scarlet 9 80 
    Vivek 9 84 
    Aamina 8 77 
    Belvet 8 78 
    Paige 8 74 
    Priya 8 76 
    Priyanka 8 77 
    NULL 7 64 
    NULL 7 66 
    NULL 6 55 
    NULL 4 34 
    NULL 3 24 
## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**

