## Problem

Query the smallest Northern Latitude (LAT_N) from STATION that is greater than _38.7780_ . Round your answer to _4_ decimal places.

**Input Format**

The **STATION** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

where LAT_N is the northern latitude and LONG_W is the western longitude.


## CODE:

    SELECT TOP 1 CAST(LAT_N AS DECIMAL(10,4)) 
    FROM STATION 
    WHERE LAT_N > 38.7780 
    ORDER BY LAT_N ASC;
    
## Output:
Your Output (stdout)

    38.8526    

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**



