## Problem
Query the names of all American cities in CITY with populations larger than 120000. The CountryCode for America is USA.

**Input Format**

The CITY table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

## Code
    
    SELECT NAME
    FROM CITY
    WHERE COUNTRYCODE = "USA" AND POPULATION > 120000;
    
## Output
**Expected Output**

    Scottsdale
    Corona
    Concord
    Cedar Rapids

## Discuss
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**
