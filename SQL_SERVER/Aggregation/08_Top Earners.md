## Problem

We define an employee's total earnings to be their monthly **_salary x months_** worked, and the maximum total earnings to be the maximum total earnings for any employee in the **Employee** table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as **_2_** space-separated integers.

**Input Format**

The **Employee** table containing employee data for a company is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/19629/1458557872-4396838885-ScreenShot2016-03-21at4.27.13PM.png)

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.

**Sample Input**

![](https://s3.amazonaws.com/hr-challenge-images/19631/1458559098-23bf583125-ScreenShot2016-03-21at4.32.59PM.png)

**Sample Output**

    69952 1
    
**Explanation**

The table and earnings data is depicted in the following diagram:

![](https://s3.amazonaws.com/hr-challenge-images/19631/1458559218-9f37585c7a-ScreenShot2016-03-21at4.49.23PM.png)

The maximum earnings value is **_69952_**. The only employee with earnings **_= 69952_** is Kimberly, so we print the maximum earnings value (**_69952_**) and a count of the number of employees who have earned **_$69952_** (which is **_1_**) as two space-separated values.

## CODE:

    SELECT MAX(MONTHS*SALARY), COUNT(EMPLOYEE_ID) 
    FROM EMPLOYEE 
    WHERE MONTHS*SALARY=(SELECT MAX( MONTHS*SALARY) FROM EMPLOYEE);
    
## Output:
Your Output (stdout)

    108064 7 

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**


