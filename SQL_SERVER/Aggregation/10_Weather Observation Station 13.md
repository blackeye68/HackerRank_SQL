## Problem

Query the sum of Northern Latitudes (LAT_N) from **STATION** having values greater than _38.7780_ and less than _137.2345_. Truncate your answer to _4_ decimal places.

**Input Format**

The **STATION** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

where _LAT_N_ is the northern latitude and _LONG_W_ is the western longitude.

## CODE:

    SELECT CAST(SUM(LAT_N) AS DECIMAL(12,4)) 
    FROM STATION 
    WHERE LAT_N BETWEEN 38.7880 AND 137.2345;
    
## Output:
Your Output (stdout)

    36354.8135   

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**



