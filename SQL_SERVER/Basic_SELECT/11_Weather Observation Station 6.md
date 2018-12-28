## Problem

 Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from **STATION**. Your result cannot contain duplicates.
 
 **Input Format:**
 
 The **STATION** table is described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

where LAT_N is the northern latitude and LONG_W is the western longitude.

## CODE:

    SELECT DISTINCT(CITY) FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' 
    OR CITY LIKE 'U%' ORDER BY CITY ASC;
    
## Output:
Your Output (stdout)

    Acme 
    Addison 
    Agency 
    Aguanga 
    Alanson 
    Alba 
    Albany 
    Albion 
    Algonac 
    Aliso Viejo 
    Allerton 
    Alpine 
    Alton 
    Amazonia 
    Amo 
    Andersonville 
    Andover 
    Anthony 
    Archie 
    Arispe 
    Arkadelphia 
    Arlington 
    Arrowsmith 
    Athens 
    Atlantic Mine 
    Auburn 
    East China 
    East Haddam 
    East Irvine 
    Eastlake 
    Edgewater 
    Effingham 
    Eleele 
    Elkton 
    Elm Grove 
    Emmett 
    Equality 
    Eriline 
    Ermine 
    Eros 
    Eskridge 
    Esmond 
    Eufaula 
    Eureka Springs 
    Eustis 
    Everton 
    Irvington 
    Oakfield 
    Oconee 
    Odin 
    Ojai 
    Olmitz 
    Onaway 
    Orange City 
    Orange Park 
    Osage City 
    Osborne 
    Oshtemo 
    Ottertail 
    Ozona 
    Udall 
    Ukiah 
    Union Star 
    Upperco 
    Urbana 
    
## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**


