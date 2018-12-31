## Problem

Julia conducted a _15_ days of learning SQL contest. The start date of the contest was March 01, 2016 and the end date was March 15, 2016.

Write a query to print total number of unique hackers who made at least _1_ submission each day (starting on the first day of the contest), and find the hacker_id and name of the hacker who made maximum number of submissions each day. If more than one such hacker has a maximum number of submissions, print the lowest hacker_id. The query should print this information for each day of the contest, sorted by the date.

---

**Input Format**

The following tables hold contest data:

* Hackers: The hacker_id is the id of the hacker, and name is the name of the hacker.

![](https://s3.amazonaws.com/hr-challenge-images/19597/1458511164-12adec3b8b-ScreenShot2016-03-21at3.26.47AM.png)

* Submissions: The submission_date is the date of the submission, submission_id is the id of the submission, hacker_id is the id of the hacker who made the submission, and score is the score of the submission. 

![](https://s3.amazonaws.com/hr-challenge-images/19597/1458511251-0b534030b9-ScreenShot2016-03-21at3.26.56AM.png)

**Sample Input**

For the following sample input, assume that the end date of the contest was March 06, 2016.

Hackers Table:

![](https://s3.amazonaws.com/hr-challenge-images/19597/1458511957-814a2c7bf2-ScreenShot2016-03-21at3.27.06AM.png)

Submissions Table: 

![](https://s3.amazonaws.com/hr-challenge-images/19597/1458512015-ff6a708164-ScreenShot2016-03-21at3.27.21AM.png)

**Sample Output**

    2016-03-01 4 20703 Angela
    2016-03-02 2 79722 Michael
    2016-03-03 2 20703 Angela
    2016-03-04 2 20703 Angela
    2016-03-05 1 36396 Frank
    2016-03-06 1 20703 Angela

**Explanation**

On March 01, 2016 hackers **_20703_**, **_36396_** , **_53473_** , and **_79722_** made submissions. There are **_4_** unique hackers who made at least one submission each day. As each hacker made one submission, **_20703_** is considered to be the hacker who made maximum number of submissions on this day. The name of the hacker is Angela.

On March 02, 2016 hackers **_15758_** , **_20703_** , and **_79722_** made submissions. Now **_20703_**  and **_79722_** were the only ones to submit every day, so there are **_2_** unique hackers who made at least one submission each day. **_79722_** made **_2_** submissions, and name of the hacker is Michael.

On March 03, 2016 hackers **_20703_**, **_36396_**, **_79722_** and **_15758_** made submissions. Now **_20703_** and **_79722_** were the only ones, so there are **_2_**  unique hackers who made at least one submission each day. As each hacker made one submission so **_20703_** is considered to be the hacker who made maximum number of submissions on this day. The name of the hacker is Angela.

On March 04, 2016 hackers **_20703_**, **_44065_**, **_53473_**, and **_79722_** made submissions. Now **_20703_** and **_79722_** only submitted each day, so there are **_2_** unique hackers who made at least one submission each day. As each hacker made one submission so **_20703_** is considered to be the hacker who made maximum number of submissions on this day. The name of the hacker is Angela.

On March 05, 2016 hackers **_20703_**, **_36396_**, **_38289_** and **_62529_** made submissions. Now **_20703_** only submitted each day, so there is only **_1_** unique hacker who made at least one submission each day. **_36396_** made **_2_** submissions and name of the hacker is Frank.

On March 06, 2016 only **_20703_** made submission, so there is only **_1_** unique hacker who made at least one submission each day. **_20703_** made **_1_** submission and name of the hacker is Angela.

&‌equiv;

## CODE:

    select table2.submission_date, table2.Unique_Count, table1.hacker_id , hackers.name 
    from hackers, 
    (select * 
    from (select submission_date, hacker_id ,row_number() over (partition by submission_date order by count desc,hacker_id asc) as rn
    from
    (select submission_date, hacker_id, count(*) as count from submissions 
    group by submission_date,hacker_id 
    having count(*) >= 1 
    ) a
    ) b
    where rn=1 ) table1,

    (
    SELECT submission_date, COUNT(DISTINCT hacker_id) Unique_Count
    from (
    SELECT d.submission_date, v.hacker_id, COUNT(DISTINCT v.submission_date) cnt
    fROM
    (SELECT DISTINCT submission_date FROM Submissions 
    ) d,
    submissions v
    where v.submission_date <= d.submission_date
    GROUP BY d.submission_date, v.hacker_id
        ) e
    WHERE Convert(Varchar(Max),day(submission_date)) = cnt GROUP BY submission_date 
        ) table2
    where hackers.hacker_id = table1.hacker_id 
    and table1.submission_date = table2.submission_date 
    order by table1.submission_date;
    
## Output:
Your Output (stdout)

    2016-03-01 112 81314 Denise 
    2016-03-02 59 39091 Ruby 
    2016-03-03 51 18105 Roy 
    2016-03-04 49 533 Patrick 
    2016-03-05 49 7891 Stephanie 
    2016-03-06 49 84307 Evelyn 
    2016-03-07 35 80682 Deborah 
    2016-03-08 35 10985 Timothy 
    2016-03-09 35 31221 Susan 
    2016-03-10 35 43192 Bobby 
    2016-03-11 35 3178 Melissa 
    2016-03-12 35 54967 Kenneth 
    2016-03-13 35 30061 Julia 
    2016-03-14 35 32353 Rose 
    2016-03-15 35 27789 Helen 

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**
