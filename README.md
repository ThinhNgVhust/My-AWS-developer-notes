# My-AWS-developer-notes
```javascript
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


