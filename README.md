# Hướng dẫn tạo Django project với Machine Learning

## Chuẩn bị môi trường

0. Giả sử bạn đang ở trong thư mục tên là `<folder_name>`
1. Tạo môi trường ảo:
   ```
   python -m venv .venv
   ```
2. Kích hoạt môi trường ảo:
   - Windows: `.venv\Scripts\activate`
   - macOS/Linux: `source .venv/bin/activate`

## Cài đặt Django và tạo project

3. Cài đặt Django:
   ```
   pip install django
   ```
4. Tạo project Django:
   ```
   django-admin startproject <project_name> .
   ```
   Cấu trúc thư mục của project:
   ```
   <folder_name>/
       manage.py
       <project_name>/
           __init__.py
           settings.py
           urls.py
           wsgi.py
           asgi.py
   ```

## Cài đặt các dependencies

5. Tạo file `requirements.txt`:
   ```
   pip freeze > requirements.txt
   ```
6. Tạo app API:
   ```
   python manage.py startapp api
   ```
7. Cài đặt các thư viện cần thiết:
   ```
   pip install django-environ psycopg2-binary django-cors-headers gunicorn djangorestframework whitenoise
   ```
8. Nếu tích hợp Machine Learning, cài đặt thêm:
   ```
   pip install numpy pandas scikit-learn
   ```

## Cấu trúc project cho Machine Learning

9. Tạo các thư mục cho ML:
   ```
   mkdir notebooks trained_models data
   ```

## Cấu hình database và môi trường

10. Chạy migration:
    ```
    python manage.py migrate
    ```
11. Tạo file môi trường:
    - Tạo file `.env` và `.env.example`
    - Tạo file `.gitignore`

## Cấu hình settings.py

12. Cập nhật file `settings.py` (xem phần settings.py bên dưới)

## Khởi chạy server

13. Chạy server phát triển:
    ```
    python manage.py runserver
    ```

## Lưu ý bảo mật

- Không commit file `.env` lên git
- Sử dụng biến môi trường cho các thông tin nhạy cảm
- Tắt DEBUG mode trong môi trường production

## Tài liệu tham khảo

- [Django Documentation](https://docs.djangoproject.com/)
- [Django REST Framework](https://www.django-rest-framework.org/)
- [Scikit-learn Documentation](https://scikit-learn.org/stable/documentation.html)
