## Problem

Query the Western Longitude (LONG_W)where the smallest Northern Latitude (LAT_N) in **STATION** is greater than _38.7780_ . Round your answer to _4_ decimal places.

**Input Format**

The **STATION** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

where LAT_N is the northern latitude and LONG_W is the western longitude.

## CODE:

    SELECT CAST(LONG_W AS DECIMAL(20,4)) FROM STATION WHERE LAT_N = (SELECT MIN(LAT_N) 
    FROM STATION 
    WHERE LAT_N > 38.7780);
    
## Output:
Your Output (stdout)

    70.1378 

    

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**



