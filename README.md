# My-AWS-developer-notes
```javascript
 $("#ajaxButton").click(function () {
            $.ajax({
                url: '/YourController/YourAction', // Không cần URL hoàn chỉnh
                type: 'GET',
                success: function (data) {
                    $("#result").html(data);
                },
                error: function () {
                    alert("Error occurred.");
                }
            });
        });
```
