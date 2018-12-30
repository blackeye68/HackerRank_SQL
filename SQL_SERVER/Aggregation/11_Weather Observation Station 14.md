## Problem

Query the greatest value of the Northern Latitudes (LAT_N) from **STATION** that is less than _137.2345_ . Truncate your answer to _4_ decimal places.

**Input Format**

The **STATION** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

where _LAT_N_ is the northern latitude and _LONG_W_ is the western longitude.

## CODE:

    SELECT MAX(CAST(ROUND(LAT_N,4,0)AS DECIMAL(18,4))) 
    FROM STATION 
    WHERE LAT_N<137.2345;
    
## Output:
Your Output (stdout)

    137.0193    

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**



