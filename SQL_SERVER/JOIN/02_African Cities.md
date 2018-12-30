# Problem

Given the **CITY** and **COUNTRY** tables, query the names of all cities where the CONTINENT is 'Africa'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

**Input Format**

The **CITY** and **COUNTRY** tables are described as follows: 

![](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

![](https://s3.amazonaws.com/hr-challenge-images/8342/1449769013-e54ce90480-Country.jpg)

## CODE:


    SELECT city.name
    FROM city
    JOIN country
    ON city.countrycode = country.code
    WHERE continent = 'Africa';
    
## Output:
Your Output (stdout)

    Qina 
    Warraq al-Arab 
    Kempton Park 
    Alberton 
    Klerksdorp 
    Uitenhage 
    Brakpan 
    Libreville

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**
