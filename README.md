# CookieHanHoan

## Simple SQL Injection Bypass Login

  > ![image](https://github.com/JCiculs/CookieHanHoan/assets/121303094/8ee7daa8-b5e2-41e4-b6c6-940d063c09ee)

- Bài đã cho trước user và password của guest. Sau khi đăng nhập thì ta thấy có 1 alert "Hello guest" xuất hiện.
- Thử syntax `'` thì thấy server báo wrong -> phải đổi syntax
- Thử lại bằng `"` thì e thấy trả về 500. -> đúng.
- Áp dụng vào bài thì có payload `admin"or"1=1";--`

  > ![image](https://github.com/JCiculs/CookieHanHoan/assets/121303094/aae1f22a-05e2-4d81-967c-a803c127b216)

- Chúng ta đã đăng nhập được nhưng tại sao lại báo guest?
- Có lẽ bài yêu cầu >= 2 giá trị mới được.
- Em thử sử dụng payload `"UNION+SELECT+NULL,NULL;--` để kiểm tra kiểu dữ liệu và số column thì đúng.

  > ![image](https://github.com/JCiculs/CookieHanHoan/assets/121303094/2689827c-2f9c-4cd6-b3f1-e3a5a9038d0c)

- Điền thử chữ `a` vào thì thấy cả 2 column đều là string.

  > ![image](https://github.com/JCiculs/CookieHanHoan/assets/121303094/12d4c710-ac58-4cbc-89fd-9cf041d43b88)

- Vì quá lười nên em điền luôn `admin` vào column đầu và giải ra flag. =)))))
- Quá là ảo ma tà đạo heheehe

> ![image](https://github.com/JCiculs/CookieHanHoan/assets/121303094/0903cc9b-e21b-4f77-8fcf-4e3bb1abb99b)
