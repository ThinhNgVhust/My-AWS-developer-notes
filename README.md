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

$(document).ready(function () {
    $("#ajaxButton").click(function () {
        $.ajax({
            url: '/YourController/GetData', // Điều chỉnh đường dẫn tương ứng
            type: 'GET',
            dataType: 'json',
            success: function (data) {
                var $table = $("<table>").addClass("table");
                var $thead = $("<thead>");
                var $tbody = $("<tbody>");

                // Tạo dòng tiêu đề (thead)
                var $headerRow = $("<tr>");
                for (var key in data[0]) {
                    $headerRow.append($("<th>").text(key));
                }
                $thead.append($headerRow);
                $table.append($thead);

                // Tạo các dòng dữ liệu (tbody)
                data.forEach(function (item) {
                    var $dataRow = $("<tr>");
                    for (var key in item) {
                        $dataRow.append($("<td>").text(item[key]));
                    }
                    $tbody.append($dataRow);
                });
                $table.append($tbody);

                // Hiển thị bảng trong phần tử có ID là "dataContainer"
                $("#dataContainer").html($table);
            },
            error: function () {
                alert("Error occurred.");
            }
        });
    });
});
```
