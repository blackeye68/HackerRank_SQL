## Problem

Consider _P1(a,b)_ and _P2(b,d)_ to be two points on a 2D plane.

* _a_ happens to equal the minimum value in Northern Latitude (LAT_N in **STATION**).
* _b_ happens to equal the minimum value in Western Longitude (LONG_W in **STATION**).
* _c_ happens to equal the maximum value in Northern Latitude (LAT_N in **STATION**).
* _d_ happens to equal the maximum value in Western Longitude (LONG_W in **STATION**).

Query the [Manhattan Distance](https://en.wiktionary.org/wiki/Manhattan_distance) between points  and  and round it to a scale of  decimal places.

**Input Format**

The **STATION** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

where LAT_N is the northern latitude and LONG_W is the western longitude.

## CODE:

    SELECT FORMAT(ABS(MIN(LAT_N)-MAX(LAT_N))+ABS(MIN(LONG_W)-MAX(LONG_W)),'F4') 
    FROM STATION;
    
## Output:
Your Output (stdout)

    259.6859     

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**



