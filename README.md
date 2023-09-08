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

```cshtml
@page
@model RazorPagesMovie.Pages.Movies.IndexModel

@{
    ViewData["Title"] = "Index";
}

<h1>Index</h1>

<p>
    <a asp-page="Create">Create New</a>
</p>
@using (Html.BeginForm())
{

<table class="table">
    <thead>
        <tr>
            <th>
                @Html.DisplayNameFor(model => model.Movie[0].Title)
                    
            </th>
            <th>
                @Html.DisplayNameFor(model => model.Movie[0].ReleaseDate)
            </th>
            <th>
                @Html.DisplayNameFor(model => model.Movie[0].Genre)
            </th>
            <th>
                @Html.DisplayNameFor(model => model.Movie[0].Price)
            </th>
            <th>Gener</th>
        </tr>
    </thead>
    <tbody>

        @for(int i = 0; i <  Model.Movie.Count; i++)
        {
            var item = Model.Movie[i];
            <tr>
                <td>
                    @Model.Movie[i].Title
                        @Html.HiddenFor(modelItem => Model.Movie[i].Title)
                        @Html.HiddenFor(model => model.Movie[i].Id)
            </td>
            <td>
                    @Model.Movie[i].ReleaseDate
                        @Html.HiddenFor(modelItem => Model.Movie[i].ReleaseDate)
            </td>
            <td>
                @Model.Movie[i].Genre
                        @Html.HiddenFor(modelItem => Model.Movie[i].Genre)
            </td>
            <td>
                    @Model.Movie[i].Price
                        @Html.HiddenFor(modelItem => Model.Movie[i].Price)
            </td>

                   <td>
                        <select name="Movie[@i].Genre" asp-for="@Model.Movie[i].Genre">
                            @foreach (var genre in Model.AvailableGenres)
                            {
                                <option value="@genre">@genre</option>
                            }
                        </select>
                   </td>
                    <td><button class="deleteBtn" type="button">Delete</button></td>
                    <td>
                        <button class="moveUpBtn" type="button">Move Up</button>
                    </td>
                    <td>
                        <button class="moveDownBtn" type="button">Move Down</button>
                    </td>
        </tr>
}
    </tbody>
</table>
<hr />
  @Html.AntiForgeryToken() 
<div class="form-group">
    <div class="col-md-offset-2 col-md-10 text-center">
        <input type="submit" value="Place Order" class="btn btn-primary" />
    </div>
</div>  
}
<script type="text/javascript">
    document.addEventListener("DOMContentLoaded", function () {
        $(".deleteBtn").click(function () {
            var row = $(this).closest("tr");
            var rowIndex = row.index(); // Lấy index của dòng

            // Remove the row from the table
            row.remove();

            // Update the remaining rows' indexes and hidden input names
            $(".table tbody tr").each(function (index, element) {
                if (index >= rowIndex) {
                    var currentRow = $(element);

                    // Update hidden input names
                    currentRow.find('input[type="hidden"][name$=".Title"]').attr("name", "Movie[" + index + "].Title");
                    currentRow.find('input[type="hidden"][name$=".ReleaseDate"]').attr("name", "Movie[" + index + "].ReleaseDate");
                    currentRow.find('input[type="hidden"][name$=".Genre"]').attr("name", "Movie[" + index + "].Genre");
                    currentRow.find('input[type="hidden"][name$=".Price"]').attr("name", "Movie[" + index + "].Price");

                    // Update dropdown list names (if applicable)
                    currentRow.find('select[name^="Movie["]').attr("name", "Movie[" + index + "].Genre");
                }
            });
        });
        $(".moveUpBtn").click(function () {
            var row = $(this).closest("tr");
            var prevRow = row.prev("tr");

            if (prevRow.length) {
                prevRow.before(row);
            }
        });

        $(".moveDownBtn").click(function () {
            var row = $(this).closest("tr");
            var nextRow = row.next("tr");

            if (nextRow.length) {
                nextRow.after(row);
            }
        });
    });
</script>

```
```javascript
function areObjectsEqual(obj1, obj2) {
    const keys1 = Object.keys(obj1);
    const keys2 = Object.keys(obj2);

    if (keys1.length !== keys2.length) {
        return false;
    }

    for (const key of keys1) {
        const value1 = obj1[key];
        const value2 = obj2[key];

        if (typeof value1 === 'object' && typeof value2 === 'object') {
            // Nếu thuộc tính là đối tượng, thực hiện đệ quy để so sánh đối tượng con
            if (!areObjectsEqual(value1, value2)) {
                return false;
            }
        } else if (Array.isArray(value1) && Array.isArray(value2)) {
            // Nếu thuộc tính là danh sách (array), so sánh danh sách này
            if (!areArraysEqual(value1, value2)) {
                return false;
            }
        } else if (value1 !== value2) {
            return false;
        }
    }

    return true;
}

function areArraysEqual(arr1, arr2) {
    if (arr1.length !== arr2.length) {
        return false;
    }

    for (let i = 0; i < arr1.length; i++) {
        if (typeof arr1[i] === 'object' && typeof arr2[i] === 'object') {
            // Nếu phần tử là đối tượng, thực hiện đệ quy để so sánh đối tượng con
            if (!areObjectsEqual(arr1[i], arr2[i])) {
                return false;
            }
        } else if (arr1[i] !== arr2[i]) {
            return false;
        }
    }

    return true;
}

// Sử dụng hàm để so sánh hai đối tượng có danh sách
const object1 = { name: 'John', addresses: [{ city: 'New York', zip: '10001' }] };
const object2 = { name: 'John', addresses: [{ city: 'New York', zip: '10001' }] };
const object3 = { name: 'Jane', addresses: [{ city: 'Los Angeles', zip: '90001' }] };

console.log(areObjectsEqual(object1, object2)); // true
console.log(areObjectsEqual(object1, object3)); // false
```
