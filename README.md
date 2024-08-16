# Position trong CSS
Thuộc tính **position** xác định loại phương pháp định vị được sử dụng cho một phần tử.

Có **5** loại giá trị vị trí khác nhau:
- static
- relative
- fixed
- absolute
- sticky

## 1. Static
- Đây là giá trị **mặc định** cho tất cả các phần tử.
- Khi một phần tử có `position: static;` nó được đặt theo dòng chảy thông thường của trang, *tức là theo thứ tự xuất hiện trong HTML*.
- Không bị ảnh hưởng bởi `top, right, bottom, left hoặc z-index.`
- Ứng dụng phổ biến: `position: static;` thường được sử dụng cho các phần tử không cần định vị đặc biệt, chẳng hạn như *đoạn văn bản, hình ảnh trong một bài viết hoặc cần bất kỳ phần tử nào không được đặt ở vị trí cụ thể*.
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
- **Vị trí tương đối:** Tương tự như `static` nhưng có thể được dịch chuyển ra khỏi vị trí ban đầu bằng cách sử dụng các thuộc tính như `top, right, bottom, left`. 
- **Lưu ý**: Sự dịch chuyển này **không ảnh hưởng** đến các vị trí của các phần tử xung quanh nó, chúng vẫn coi phần tử này ở vị trí ban đầu.
- Ứng dụng phổ biến: `position: relative;` thường được sử dụng khi bạn muốn *di chuyển một phần tử khỏi vị trí ban đầu của nó mà không làm ảnh hưởng đến bố cục của các phần tử xung quanh*.
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

## 3. Absolute
- **Vị trí tuyệt đối:** Phần tử sẽ được đặt theo một trong các phần tử tổ tiên của nó mà có `position` khác `static`. Nếu không có tổ tiên nào có `position` khác `static` thì nó sẽ được đặt theo `body`.
- **Lưu ý:** `position: absolute;` *thoát khỏi dòng chảy* của tài liệu và không ảnh hưởng đến các phần tử khác.
- Ứng dụng phổ biến: `position: absolute;` thường được sử dụng để tạo các phần tử nổi như hộp thông báo, hộp thoại hoặc menu thả xuống, nơi cần định vị phần tử ở vị trí cụ thể trên trang mà không ảnh hưởng đến vị trí của các phần tử khác.
- **absolute.html:**
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aboslute || Position</title>

    <style>
        .container {
            position: relative;
            width: 300px;
            height: 300px;
            background-color: lightgray;
        }

        .box {
            width: 100px;
            height: 100px;
            background-color: lightsalmon;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
    </style>
</head>

<body>
    <div class="container"> Relative
        <div class="box">Absolute</div>
    </div>
</body>

</html>
```
- Mở file `absolute.html` trên trình duyệt, bạn sẽ thấy output như sau:

![absolute.html](/images/absolute.png)

## 4. Fixed

- **Vị trí cố định:** Phần tử được đặt ở một vị trí cố định so với cửa sổ trình duyệt, ngay cả khi cuộn trang. Điều này có nghĩa là **phần tử sẽ luôn xuất hiện ở cùng một vị trí trên màn hình**, bất kể người dùng cuộn trang đến đâu.
- **Lưu ý:** `position: fixed;` tương tự như `position: absolute;`cũng *thoát khỏi dòng chảy* của tài liệu và không ảnh hưởng đến các phần tử khác.
- Ứng dụng phổ biến: `position: fixed;` thường được sử dụng cho các *thanh điều hướng cố định, chân trang (footer) cố định, v.v*.
- **fixed.html:**
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fixed || Position</title>

    <style>
        .container {
            width: 100%;
            height: 1500px;
            background-color: gray;
        }

        .fixed {
            width: 300px;
            height: 100px;
            background-color: coral;
            position: fixed;
            top: 10px;
            right: 10px;
        }

        .bottom {
            width: 100%;
            height: 20px;
            background-color: red;
            text-align: center;
        }
    </style>
</head>

<body>
    <div class="container">
        <div class="fixed">Fixed</div>
    </div>
    <div class="bottom">bottom</div>
</body>

</html>
```

- Mở file `fixed.html` trên trình duyệt, bạn sẽ thấy output như sau:

![fixed.html](/images/fixed1.png)

Dễ thấy ngay cả khi cuộn hết trang thì vị trí của `Fixed` vẫn không hề thay đổi.

![fixed.html](/images/fixed2.png)


## 5. Sticky

- **Vị trí dính:** Đây là một sự kết hợp giữa `relative` và `fixed`. `position: sticky;` sẽ hoạt động **giống như** `relative` cho đến khi *một điều kiện cuộn nhất định được thoả mãn* (khi phần tử cuộn đến vị trí nhất định nó sẽ trở nên **dính** và sẽ hoạt động giống như `fixed`)
- Ứng dụng phổ biến: `position: sticky;` thường được sử dụng cho các *thanh điều hướng (navbar), tiêu đề của các phần (section headers), hoặc các phần tử cần được giữ cố định trong tầm nhìn của người dùng khi cuộn trang*.
- **sticky.html:**
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sticky || Position</title>

    <style>
        .box {
            width: 100%;
            height: 50px;
            background-color: yellow;
            top: 0;
            position: sticky;
        }
        .content {
            height: 1500px;
            background-color: lightgray;
        }
    </style>
</head>
<body>
    <div class="box">Sticky</div>
    <div class="content">Scroll down to see the sticky effect...</div>
</body>
</html>
```
- Mở file `sticky.html` trên trình duyệt, bạn sẽ thấy output như sau:

![sticky.html](/images/sticky1.png)

Sau khi cuộn hết trang:

![sticky.html](/images/sticky2.png)


> Trên đây là lý thuyết cơ bản về `position` trong CSS, các bạn cần thực hành nhiều để hiểu về nó. Cảm ơn mọi người đã đọc...
