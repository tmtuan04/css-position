# Position trong CSS
Thuộc tính **position** xác định loại phương pháp định vị được sử dụng cho một phần tử.

Có **5** loại giá trị vị trí khác nhau:
- static
- relative
- fixed
- absolute
- sticky

## 1. Static
- Đây là giá trị **mặc định** cho tất cả các phần tử, khi một phần tử có `position: static;` nó được đặt theo dòng chảy thông thường của trang, *tức là theo thứ tự xuất hiện trong HTML*.
- Không bị ảnh hưởng bởi `top, right, bottom, left hoặc z-index.`
- **static.html:**
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Static || Position</title>

    <style>
        .static {
            width: 100px;
            height: 100px;
            background-color: aquamarine;
            position: static;
            /* Nó sẽ không bị ảnh hưởng bởi 2 dòng bên dưới */
            top: 20px;
            left: 20px;
        }
    </style>
</head>

<body>
    <div class="static">Static</div>
</body>

</html>
```
- Mở file `static.html` trên trình duyệt, bạn sẽ thấy output như sau: 
![static.html](/images/static.png)

## 2. Relative
- **Vị trí tương đối:** Tương tự như `static` nhưng có thể được dịch chuyển ra khỏi vị trí ban đầu bằng cách sử dụng các thuộc tính như `top, right, bottom, left.` 
- **Lưu ý**: Sự dịch chuyển này **không ảnh hưởng** đến các vị trí của các phần tử xung quanh nó, chúng vẫn coi phần tử này ở vị trí ban đầu.
- **relative.html:**
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Relatieve || Position</title>

    <style>
        .relative {
            width: 300px;
            height: 100px;
            background-color: lightgreen;
            position: relative;
            /* Bị ảnh hưởng bởi 2 dòng bên dưới */
            top: 20px;
            left: 20px;
        }
    </style>
</head>

<body>
    <div class="relative">Relative</div>
</body>

</html>
```
- Mở file `relative.html` trên trình duyệt, bạn sẽ thấy output như sau: 
![relative.html](/images/relative.png)