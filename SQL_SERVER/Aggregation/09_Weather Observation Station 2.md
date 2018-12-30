## Problem

 Query the following two values from the **STATION** table:

1. The sum of all values in LAT_N rounded to a scale of  decimal places.
2. The sum of all values in LONG_W rounded to a scale of  decimal places.

**Input Format**

The **STATION** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

where _LAT_N_ is the northern latitude and _LONG_W_ is the western longitude.

**Output Format**

Your results must be in the form:

    lat lon

where  is the sum of all values in _LAT_N_ and  is the sum of all values in _LONG_W_. Both results must be rounded to a scale of  decimal places.

## CODE:

    SELECT CAST(ROUND(SUM(LAT_N), 2)AS NUMERIC(12,2)), CAST(ROUND(SUM(LONG_W), 2) AS NUMERIC(12,2)) 
    FROM STATION;
    
## Output:
Your Output (stdout)

    42850.04 47381.48 

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**



