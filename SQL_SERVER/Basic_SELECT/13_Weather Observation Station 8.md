## Problem
 
 Query the list of **CITY** names from **STATION** which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.
 
 **Input Format:**
 
 The **STATION** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

where LAT_N is the northern latitude and LONG_W is the western longitude.

## CODE:

    SELECT DISTINCT CITY 
    FROM STATION 
    WHERE (CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%') 
    AND (CITY LIKE '%a' OR CITY LIKE '%e' OR CITY LIKE '%i' OR CITY LIKE '%o' OR CITY LIKE '%u') 
    ORDER BY CITY;
    
## Output:
Your Output (stdout)

    Acme 
    Aguanga 
    Alba 
    Aliso Viejo 
    Alpine 
    Amazonia 
    Amo 
    Andersonville 
    Archie 
    Arispe 
    Arkadelphia 
    Atlantic Mine 
    East China 
    East Irvine 
    Eastlake 
    Eleele 
    Elm Grove 
    Eriline 
    Ermine 
    Eskridge 
    Eufaula 
    Oconee 
    Ojai 
    Osborne 
    Oshtemo 
    Ozona 
    Upperco 
    Urbana 
    

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**


