## Problem

 Let _N_ be the number of CITY entries in **STATION**, and let _N'_ be the number of distinct CITY names in **STATION**; query the value of _N_ - _N'_ from **STATION**. In other words, find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
 
 **Input Format:**
 
 The **STATION** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)


## CODE:

    SELECT COUNT(CITY) - COUNT(DISTINCT CITY)
    FROM STATION;
    
## Output:
Your Output (stdout)

    13

    

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**


