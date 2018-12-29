## Problem

Amber's conglomerate corporation just acquired some new companies. Each of the companies follows this hierarchy: 

![](https://s3.amazonaws.com/hr-challenge-images/19505/1458531031-249df3ae87-ScreenShot2016-03-21at8.59.56AM.png)

Given the table schemas below, write a query to print the company_code, founder name, total number of lead managers, total number of senior managers, total number of managers, and total number of employees. Order your output by ascending company_code.

**Note:**

* The tables may contain duplicate records.
* The company_code is string, so the sorting should not be numeric. For example, if the company_codes are C_1, C_2, and C_10, then the ascending company_codes will be C_1, C_10, and C_2.
---

**Input Format**

The **Employee** table containing employee data for a company is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/19629/1458557872-4396838885-ScreenShot2016-03-21at4.27.13PM.png)

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.

**Sample Input**

![](https://s3.amazonaws.com/hr-challenge-images/19629/1458558202-9a8721e44b-ScreenShot2016-03-21at4.32.59PM.png)

**Sample Output**

    Angela
    Bonnie
    Frank
    Joe
    Kimberly
    Lisa
    Michael
    Patrick
    Rose
    Todd
    
## CODE:

    SELECT NAME FROM EMPLOYEE ORDER BY NAME;
    
## Output:
Your Output (stdout)

    Alan 
    Amy 
    Andrew 
    Andrew 
    Angela 
    Ann 
    Anna 
    Lisa 
    Lori 
    Louise 
    Maria 
    Marilyn 
    Marilyn 
  

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**

