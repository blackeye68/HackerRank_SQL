## Problem

Julia asked her students to create some coding challenges. Write a query to print the hacker_id, name, and the total number of challenges created by each student. Sort your results by the total number of challenges in descending order. If more than one student created the same number of challenges, then sort the result by hacker_id. If more than one student created the same number of challenges and the count is less than the maximum number of challenges created, then exclude those students from the result.

**Input Format**

The following tables contain challenge data:

* Hackers: The hacker_id is the id of the hacker, and name is the name of the hacker. 

![](https://s3.amazonaws.com/hr-challenge-images/19506/1458521004-cb4c077dd3-ScreenShot2016-03-21at6.06.54AM.png)

* Challenges: The challenge_id is the id of the challenge, and hacker_id is the id of the student who created the challenge. 

![](https://s3.amazonaws.com/hr-challenge-images/19506/1458521079-549341d9ec-ScreenShot2016-03-21at6.07.03AM.png)

---

**Sample Input 0**

Hackers Table:  

![](https://s3.amazonaws.com/hr-challenge-images/19506/1458521384-34c6866dae-ScreenShot2016-03-21at6.07.15AM.png)

Challenges Table: 

![](https://s3.amazonaws.com/hr-challenge-images/19506/1458521410-befa8e1cd9-ScreenShot2016-03-21at6.07.25AM.png)

**Sample Output 0**

    21283 Angela 6
    88255 Patrick 5
    96196 Lisa 1
    
**Sample Input 1**

Hackers Table: 

![](https://s3.amazonaws.com/hr-challenge-images/19506/1458521469-87036deea3-ScreenShot2016-03-21at6.07.48AM.png)

Challenges Table: 

![](https://s3.amazonaws.com/hr-challenge-images/19506/1458521490-358215cf0b-ScreenShot2016-03-21at6.07.58AM.png)

**Sample Output 1**

    12299 Rose 6
    34856 Angela 6
    79345 Frank 4
    80491 Patrick 3
    81041 Lisa 1

**Explanation**

For Sample Case 0, we can get the following details: 

![](https://s3.amazonaws.com/hr-challenge-images/19506/1458521677-fd04c384c0-ScreenShot2016-03-21at6.07.38AM.png)
 
Students **5077** and **62743** both created  challenges, but the maximum number of challenges created is **6** so these students are excluded from the result.

For Sample Case 1, we can get the following details: 

![](https://s3.amazonaws.com/hr-challenge-images/19506/1458521836-24039e7523-ScreenShot2016-03-21at6.08.08AM.png)
 
Students **12299** and **34856** both created  challenges. Because **6** is the maximum number of challenges created, these students are included in the result.

## CODE:

    WITH data
    AS
    (
    SELECT c.hacker_id as id, h.name as name, count(c.hacker_id) as counter
    FROM Hackers h
    JOIN Challenges c on c.hacker_id = h.hacker_id
    GROUP BY c.hacker_id, h.name
    )
    SELECT id,name,counter
    FROM data
    WHERE
    counter=(SELECT max(counter) FROM data)
    OR
    counter in (SELECT counter FROM data
    GROUP BY counter
    HAVING count(counter)=1 )
    ORDER BY counter desc, id;
    
## Output:
Your Output (stdout)

    5120 Julia 50 
    18425 Anna 50 
    20023 Brian 50 
    33625 Jason 50 
    41805 Benjamin 50 
    52462 Nicholas 50 
    64036 Craig 50 
    69471 Michelle 50 
    77173 Mildred 50 
    94278 Dennis 50 
    96009 Russell 50 
    96716 Emily 50 
    72866 Eugene 42 
    37068 Patrick 41 
    12766 Jacqueline 40 
    86280 Beverly 37 
    19835 Joyce 36 
    38316 Walter 35 
    29483 Jeffrey 34 
    23428 Arthur 33 
    95437 George 32 
    46963 Barbara 31 
    87524 Norma 30 
    84085 Johnny 29 
    39582 Maria 28 
    65843 Thomas 27 
    5443 Paul 26 
    52965 Bobby 25 
    77105 Diana 24 
    33787 Susan 23 
    45855 Clarence 22 
    33177 Jane 21 
    7302 Victor 20 
    54461 Janet 19 
    42277 Sara 18 
    99388 Mary 16 
    31426 Carlos 15 
    95010 Victor 14 
    27071 Gerald 10 
    90267 Edward 9 
    72609 Bobby 8 

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**

