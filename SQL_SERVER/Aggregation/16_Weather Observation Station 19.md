## Problem

Consider _P1(a,c)_ and _P2(b,d)_ to be two points on a 2D plane where _(a,b)_ are the respective minimum and maximum values of Northern Latitude (LAT_N) and _(c,d)_ are the respective minimum and maximum values of Western Longitude (LONG_W) in STATION.

Query the [Euclidean Distance](https://en.wikipedia.org/wiki/Euclidean_distance) between points  and _P1_ and _P2_ format your answer to display _4_ decimal digits.

**Input Format**

The **STATION** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

where LAT_N is the northern latitude and LONG_W is the western longitude.

## CODE:

    SELECT FORMAT(SQRT(POWER(MIN(LAT_N)-MAX(LAT_N), 2) + POWER(MIN(LONG_W)-MAX(LONG_W), 2)), 'F4') 
    FROM STATION;
    
## Output:
Your Output (stdout)

    184.1616    

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**



