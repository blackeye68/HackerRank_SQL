## Problem

Samantha interviews many candidates from different colleges using coding challenges and contests. Write a query to print the contest_id, hacker_id, name, and the sums of total_submissions, total_accepted_submissions, total_views, and total_unique_views for each contest sorted by contest_id. Exclude the contest from the result if all four sums are _**0**_.

**Note**: A specific contest can be used to screen candidates at more than one college, but each college only holds _**1**_ screening contest.
---

**Input Format**

The following tables hold interview data:

* Contests: The contest_id is the id of the contest, hacker_id is the id of the hacker who created the contest, and name is the name of the hacker. 

![](https://s3.amazonaws.com/hr-challenge-images/19596/1458517426-e017c3460e-ScreenShot2016-03-21at4.57.47AM.png)

* Colleges: The college_id is the id of the college, and contest_id is the id of the contest that Samantha used to screen the candidates. 

![](https://s3.amazonaws.com/hr-challenge-images/19596/1458517503-fd4aa63111-ScreenShot2016-03-21at4.57.56AM.png)

* Challenges: The challenge_id is the id of the challenge that belongs to one of the contests whose contest_id Samantha forgot, and college_id is the id of the college where the challenge was given to candidates. 

![](https://s3.amazonaws.com/hr-challenge-images/19596/1458517661-a642f750ce-ScreenShot2016-03-21at4.58.04AM.png)

* View_Stats: The challenge_id is the id of the challenge, total_views is the number of times the challenge was viewed by candidates, and total_unique_views is the number of times the challenge was viewed by unique candidates. 

![](https://s3.amazonaws.com/hr-challenge-images/19596/1458517983-b4302286a8-ScreenShot2016-03-21at4.58.15AM.png)

* Submission_Stats: The challenge_id is the id of the challenge, total_submissions is the number of submissions for the challenge, and total_accepted_submission is the number of submissions that achieved full scores. 

![](https://s3.amazonaws.com/hr-challenge-images/19596/1458518090-80983c916a-ScreenShot2016-03-21at4.58.27AM.png)

**Sample Input**

Contests Table: 

![](https://s3.amazonaws.com/hr-challenge-images/19596/1458519044-d788f8a6ee-ScreenShot2016-03-21at4.58.39AM.png)

Colleges Table:

![](https://s3.amazonaws.com/hr-challenge-images/19596/1458519098-912836d6ac-ScreenShot2016-03-21at4.59.22AM.png)

Challenges Table: 

![](https://s3.amazonaws.com/hr-challenge-images/19596/1458519120-c531743caf-ScreenShot2016-03-21at4.59.32AM.png)

View_Stats Table: 

![](https://s3.amazonaws.com/hr-challenge-images/19596/1458519152-107a67866b-ScreenShot2016-03-21at4.59.43AM.png)

Submission_Stats Table: 

![](https://s3.amazonaws.com/hr-challenge-images/19596/1458519173-091aba871a-ScreenShot2016-03-21at4.59.55AM.png)

**Sample Output**

    66406 17973 Rose 111 39 156 56
    66556 79153 Angela 0 0 11 10
    94828 80275 Frank 150 38 41 15

**Explanation**

The contest **_66406_** is used in the college **_11219_**. In this college **_11219_**, challenges **_18765_** and **_47127_** are asked, so from the view and submission stats:

* Sum of total submissions **_= 27 + 56 + 28 = 111_**

* Sum of total accepted submissions **_= 10 + 18 + 11 = 39_**

* Sum of total views **_=43 + 72 + 26 + 15 = 156_**

* Sum of total unique views **_= 10 + 13 + 19 + 14 = 56_**

Similarly, we can find the sums for contests **_66556_** and **_94828_**.

## CODE:

    SELECT
     con.contest_id
    ,con.hacker_id
    ,con.name
    ,SUM(total_submissions) AS total_submissions
    ,SUM(total_accepted_submissions) AS total_accepted_submissions
    ,SUM(total_views) AS total_views
    ,SUM(total_unique_views) AS total_unique_views
    FROM Contests con
    JOIN Colleges col
        ON con.contest_id = col.contest_id
    JOIN Challenges chal
        ON col.college_id = chal.college_id
    OUTER APPLY (
            SELECT
                 SUM(total_views) AS total_views
                ,SUM(total_unique_views) AS total_unique_views
            FROM View_Stats v
            WHERE chal.challenge_id = v.challenge_id
        ) a
    OUTER APPLY (
            SELECT
                 SUM(total_submissions) AS total_submissions
                ,SUM(total_accepted_submissions) AS total_accepted_submissions
            FROM Submission_Stats s
            WHERE chal.challenge_id = s.challenge_id
        ) b
    GROUP BY
         con.contest_id
        ,con.hacker_id
        ,con.name
    ORDER BY con.contest_id;
    
## Output:
Your Output (stdout)

    845 579 Rose 1987 580 1635 566 
    858 1053 Angela 703 160 1002 384 
    883 1055 Frank 1121 319 1217 338 
    1793 2655 Patrick 1337 360 1216 412 
    2374 2765 Lisa 2733 815 3368 904 
    2963 2845 Kimberly 4306 1221 3603 1184 
    3584 2873 Bonnie 2492 652 3019 954 
    4044 3067 Michael 1323 449 1722 528 
    4249 3116 Todd 1452 376 1767 463 
    4269 3256 Joe 1018 372 1766 530 
    4483 3386 Earl 1911 572 1644 477 
    4541 3608 Robert 1886 516 1694 504 
    4601 3868 Amy 1900 639 1738 548 
    4710 4255 Pamela 2752 639 2378 705 
    4982 5639 Maria 2705 759 2558 711 
    5913 5669 Joe 2646 790 3181 835 
    5994 5713 Linda 3369 967 3048 954 
    6939 6550 Melissa 2842 859 3574 1004 
    7266 6947 Carol 2758 665 3044 835 
    7280 7030 Paula 1963 554 886 259 
    7484 7033 Marilyn 3217 934 3795 1061 
    7734 7386 Jennifer 3780 1015 3637 1099 
    7831 7787 Harry 3190 883 2933 1012 
    7862 8029 David 1738 476 1475 472 
    8812 8147 Julia 1044 302 819 266 
    8825 8438 Kevin 2624 772 2187 689 
    9136 8727 Paul 4205 1359 3125 954 
    9613 8762 James 3438 943 3620 1046 
    10568 8802 Kelly 1907 620 2577 798 
    11100 8809 Robin 1929 613 1883 619 
    12742 9203 Ralph 1523 413 1344 383 
    12861 9644 Gloria 1596 536 2089 623 
    12865 10108 Victor 2076 597 1259 418 
    13503 10803 David 924 251 584 167 
    13537 11390 Joyce 1381 497 1784 538 
    13612 12592 Donna 1981 550 1487 465 
    14502 12923 Michelle 1510 463 1830 545 
    14867 13017 Stephanie 2471 676 2291 574 
    15164 13256 Gerald 2570 820 2085 607 
    15804 13421 Walter 1454 459 1396 476 
    15891 13569 Christina 2188 710 2266 786 
    16063 14287 Brandon 1804 580 1621 521 
    16415 14311 Elizabeth 4535 1366 3631 1071 
    18477 14440 Joseph 1320 391 1419 428 
    18855 16973 Lawrence 2967 1020 3371 1011 
    19097 17123 Marilyn 2956 807 2554 750 
    19575 17562 Lori 2590 863 2627 760 

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**
