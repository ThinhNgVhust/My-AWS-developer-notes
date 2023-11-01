# My-AWS-developer-notes
```javascript
<!DOCTYPE html>
<html>
<head>
    <title>Restrict Input to Numbers and One Dot</title>
</head>
<body>
    <input type="text" class="classname" placeholder="Enter text" />
    <input type="text" class="classname" placeholder="Enter text" />
    <input type="text" class="classname" placeholder="Enter text" />

    <script>
        // Lấy tất cả các phần tử input có class "classname"
        var textboxes = document.querySelectorAll(".classname");

        // Đặt sự kiện oninput cho mỗi textbox
        for (var i = 0; i < textboxes.length; i++) {
            textboxes[i].addEventListener('input', function (e) {
                // Lấy giá trị hiện tại của textbox
                var value = this.value;

                // Loại bỏ tất cả các ký tự không phải số hoặc dấu chấm
                var cleanValue = value.replace(/[^\d.]/g, '');

                // Kiểm tra xem đã có nhiều hơn 1 dấu chấm trong giá trị
                if (cleanValue.split('.').length > 2) {
                    cleanValue = cleanValue.slice(0, -1); // Loại bỏ ký tự thừa
                }

                // Cập nhật giá trị của textbox
                this.value = cleanValue;
            });
        }
    </script>
</body>
</html>


function hasCookie(cookieName, cookieValue) {
    // Lấy danh sách tất cả cookies và chia thành mảng các cookies
    var cookies = document.cookie.split(';');
    
    // Duyệt qua từng cookie
    for (var i = 0; i < cookies.length; i++) {
        var cookie = cookies[i];
        // Loại bỏ khoảng trắng ở đầu cookie
        while (cookie.charAt(0) == ' ') {
            cookie = cookie.substring(1);
        }
        
        // Kiểm tra xem cookie có bắt đầu bằng tên của chúng ta
        if (cookie.indexOf(cookieName + '=') === 0) {
            // Lấy giá trị của cookie
            var value = cookie.substring(cookieName.length + 1);
            // So sánh giá trị với giá trị cần kiểm tra
            return value === cookieValue;
        }
    }
    // Trả về false nếu không tìm thấy cookie hoặc giá trị không khớp
    return false;
}

// Đặt một cookie với tên, giá trị và các tùy chọn
function setCookie(cookieName, cookieValue, daysToExpire) {
    var expirationDate = new Date();
    expirationDate.setDate(expirationDate.getDate() + daysToExpire);

    var cookieString = cookieName + "=" + cookieValue + "; expires=" + expirationDate.toUTCString() + "; path=/";
    document.cookie = cookieString;
}
setCookie("myCookie", "Hello, World!", 30); // Đặt một cookie có tên "myCookie" với giá trị "Hello, World!" và thời hạn 30 ngày.

private async Task ReadCookie()
{
    cookieValue = await JSRuntime.InvokeAsync<string>("getCookie", "yourCookieName");
}
```


