## Problem
 Query all columns for all American cities in CITY with populations larger than 100000. The CountryCode for America is USA.
 **Input Format:**

![](https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg)

The **CITY** table is described as follows:

## CODE:

    SELECT * FROM CITY WHERE COUNTRYCODE = 'USA' AND Population>100000;
    
    SELECT * FROM CITY WHERE POPULATION > 100000 AND COUNTRYCODE = 'USA';
    
## Output:
Your Output (stdout)

    3878 Scottsdale USA Arizona 202705 
    3965 Corona USA California 124966 
    3973 Concord USA California 121780 
    3977 Cedar Rapids USA Iowa 120758 
    3982 Coral Springs USA Florida 117549
    
Expected Output

    3878 Scottsdale USA Arizona 202705 
    3965 Corona USA California 124966 
    3973 Concord USA California 121780 
    3977 Cedar Rapids USA Iowa 120758 
    3982 Coral Springs USA Florida 117549
    

## DISCUSS:
### Yêu cầu của bài: truy vấn tất cả cột đối với tất cả thành phố của American trong CITY với dân số lớn hơn 100000. Mã CountryCode của American là USA.
- **Tư duy:** 
- **Phân tích:**
- **Kiến thức áp dụng:**
- **Lưu ý:**
- Cần thêm ; ở cuối để dòng code có hiệu quả
- Đối với chuỗi trong Code (như trên là USA) phải đặt giữa '' hoặc "" đều được.
- * đại diện cho tìm tất cả các column

