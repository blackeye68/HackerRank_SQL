# Problem

Given the **CITY** and **COUNTRY** tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.

**Note**: CITY.CountryCode and COUNTRY.Code are matching key columns.

**Input Format**

The **CITY** and **COUNTRY** tables are described as follows:

![](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

![](https://s3.amazonaws.com/hr-challenge-images/8342/1449769013-e54ce90480-Country.jpg)

## CODE:

    SELECT COUNTRY.CONTINENT, FLOOR(AVG(CITY.POPULATION)) 
    FROM CITY JOIN COUNTRY ON CITY.COUNTRYCODE = COUNTRY.CODE 
    WHERE CITY.NAME IS NOT NULL GROUP BY COUNTRY.CONTINENT;
    
## Output:
Your Output (stdout)

    Africa 274439 
    Asia 693038 
    Europe 175138 
    Oceania 109189 
    South America 147435

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**

