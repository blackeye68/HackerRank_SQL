## Problem

Samantha was tasked with calculating the average monthly salaries for all employees in the **EMPLOYEES** table, but did not realize her keyboard's _0_ key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeroes removed), and the actual average salary.

Write a query calculating the amount of error (i.e.: **_actual-miscalculated_** average monthly salaries), and round it up to the next integer.

**Input Format**

The **EMPLOYEES** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/12893/1443817108-adc2235c81-1.png)

**Note**: Salary is measured in dollars per month and its value is < 10^5 (10 mũ 5) .

**Sample Input**

![](https://s3.amazonaws.com/hr-challenge-images/12893/1443817161-299cc6eb7f-2.png)

**Sample Output**

    2061

**Explanation**

The table below shows the salaries without zeroes as they were entered by Samantha:

![](https://s3.amazonaws.com/hr-challenge-images/12893/1443817229-eb00d44a3b-3.png)

Samantha computes an average salary of **_98.00_**. The actual average salary is **_2159.00_**.

The resulting error between the two calculations is **_2159.00 - 98.00 = 2061.00_** which, when rounded to the next integer, is **_2061_**.

## CODE:

    SELECT CEILING(AVG(SALARY - CAST(REPLACE(CAST(SALARY AS VARCHAR(10)), '0', '') AS DECIMAL(10,4)))) 
    FROM EMPLOYEES;
    
## Output:
Your Output (stdout)

    2253 

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**


