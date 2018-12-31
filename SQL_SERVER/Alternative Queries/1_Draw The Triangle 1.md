## Problem

P(R) represents a pattern drawn by Julia in R rows. The following pattern represents P(5):

    * * * * * 
    * * * * 
    * * * 
    * * 
    *

Write a query to print the pattern P(20).

## CODE:

    DECLARE @i INT = 20
    WHILE (@i > 0) 
    BEGIN
       PRINT REPLICATE('* ', @i) 
       SET @i = @i - 1
    END;
    
## Output:
Your Output (stdout)

    * * * * * * * * * * * * * * * * * * * * 
    * * * * * * * * * * * * * * * * * * * 
    * * * * * * * * * * * * * * * * * * 
    * * * * * * * * * * * * * * * * * 
    * * * * * * * * * * * * * * * * 
    * * * * * * * * * * * * * * * 
    * * * * * * * * * * * * * * 
    * * * * * * * * * * * * * 
    * * * * * * * * * * * * 
    * * * * * * * * * * * 
    * * * * * * * * * * 
    * * * * * * * * * 
    * * * * * * * * 
    * * * * * * * 
    * * * * * * 
    * * * * * 
    * * * * 
    * * * 
    * * 
    * 

## DISCUSS:
### Yêu cầu của bài: 
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**

