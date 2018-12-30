## Problem

Julia just finished conducting a coding contest, and she needs your help assembling the leaderboard! Write a query to print the respective hacker_id and name of hackers who achieved full scores for more than one challenge. Order your output in descending order by the total number of challenges in which the hacker earned a full score. If more than one hacker received full scores in same number of challenges, then sort them by ascending hacker_id.

**Input Format**

The following tables contain contest data:

* Hackers: The hacker_id is the id of the hacker, and name is the name of the hacker. 

![](https://s3.amazonaws.com/hr-challenge-images/19504/1458526776-67667350b4-ScreenShot2016-03-21at7.45.59AM.png)

* Difficulty: The difficult_level is the level of difficulty of the challenge, and score is the score of the challenge for the difficulty level. 

![](https://s3.amazonaws.com/hr-challenge-images/19504/1458526915-57eb75d9a2-ScreenShot2016-03-21at7.46.09AM.png)

* Challenges: The challenge_id is the id of the challenge, the hacker_id is the id of the hacker who created the challenge, and difficulty_level is the level of difficulty of the challenge. 

![](https://s3.amazonaws.com/hr-challenge-images/19504/1458527032-f9ca650442-ScreenShot2016-03-21at7.46.17AM.png)

* Submissions: The submission_id is the id of the submission, hacker_id is the id of the hacker who made the submission, challenge_id is the id of the challenge that the submission belongs to, and score is the score of the submission. 

![](https://s3.amazonaws.com/hr-challenge-images/19504/1458527077-298f8e922a-ScreenShot2016-03-21at7.46.29AM.png)

---

**Sample Input**

Hackers Table:  

![](https://s3.amazonaws.com/hr-challenge-images/19504/1458527241-6922b4ad87-ScreenShot2016-03-21at7.47.02AM.png)

Difficulty Table:  

![](https://s3.amazonaws.com/hr-challenge-images/19504/1458527265-7ad6852a13-ScreenShot2016-03-21at7.46.50AM.png)

Challenges Table:  

![](https://s3.amazonaws.com/hr-challenge-images/19504/1458527285-01e95eb6ec-ScreenShot2016-03-21at7.46.40AM.png)

Submissions Table: 

![](https://s3.amazonaws.com/hr-challenge-images/19504/1458527812-479a74b99f-ScreenShot2016-03-21at8.06.05AM.png)

**Sample Output**

        90411 Joe

**Explanation**

Hacker 86870 got a score of 30 for challenge 71055 with a difficulty level of 2, so 86870 earned a full score for this challenge.

Hacker 90411 got a score of 30 for challenge 71055 with a difficulty level of 2, so 90411 earned a full score for this challenge.

Hacker 90411 got a score of 100 for challenge 66730 with a difficulty level of 6, so 90411 earned a full score for this challenge.

Only hacker 90411 managed to earn a full score for more than one challenge, so we print the their hacker_id and name as space-separated values.

## CODE:

    select h.hacker_id, h.name
    from submissions s
    inner join challenges c
    on s.challenge_id = c.challenge_id
    inner join difficulty d
    on c.difficulty_level = d.difficulty_level 
    inner join hackers h
    on s.hacker_id = h.hacker_id
    where s.score = d.score 
    group by h.hacker_id, h.name
    having count(h.hacker_id) > 1
    order by count(h.hacker_id) desc, h.hacker_id asc;
    
## Output:
Your Output (stdout)

    27232 Phillip 
    28614 Willie 
    15719 Christina 
    43892 Roy 
    14246 David 
    14372 Michelle 
    18330 Lawrence 
    26133 Jacqueline 
    26253 John 
    30128 Brandon 
    35583 Norma 
    13944 Victor 
    17295 Elizabeth 
    19076 Matthew 
    26895 Evelyn 
    32172 Jonathan 
    41293 Robin 
    45386 Christina 
    45785 Jesse 
    49652 Christine 
    13391 Robin 
    14366 Donna 
    14777 Gerald 
    16259 Brandon 
    17762 Joseph 
    28275 Debra 
    36228 Nancy 
    37704 Keith 
    40226 Anna 
    49307 Brian 
    12539 Paul 
    14363 Joyce 
    14658 Stephanie 
    19448 Jesse 
    20504 John 
    20534 Martha 
    22196 Anthony 
    23678 Kimberly 
    28299 David 
    30721 Ann 
    32254 Dorothy 
    46205 Joyce 
    47641 Patricia 
    13122 James 
    13762 Gloria 
    14863 Walter 
    18690 Marilyn 
    18983 Lori 
    21212 Timothy 
    25732 Antonio 
    28250 Evelyn 
    30755 Emily 
    38852 Benjamin 
    42052 Andrew 
    44188 Diana 
    48984 Gregory 
    13380 Kelly 
    13523 Ralph 
    21463 Christine 
    24663 Louise 
    26243 Diana 
    26289 Dorothy 
    39277 Charles 
    23278 Paula 
    25184 Martin 
    32121 Dorothy 
    36322 Andrew 
    39782 Tammy 
    40257 James 
    41319 Jean 
    10857 Kevin 
    25238 Paul 
    34242 Marilyn 
    39771 Alan 
    49789 Lillian 
    57947 Justin 
    74413 Harry  

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**
