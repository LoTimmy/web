
```
div.dataTables_wrapper {
  margin-bottom: 3em;
}
```

---

`Feature enable / disable`
```js
$(document).ready(function() {
  $("#example").DataTable({
    paging: false,
    ordering: false,
    info: false
  });
});
```

`Default ordering (sorting)`
```js
$(document).ready(function() {
  $("#example").DataTable({
    order: [[3, "desc"]]
  });
});
```

`Hidden columns`
```js
$(document).ready(function() {
  $("#example").DataTable({
    columnDefs: [
      {
        targets: [2],
        visible: false,
        searchable: false
      },
      {
        targets: [3],
        visible: false
      }
    ]
  });
});
```

`Scroll - vertical`
```js
$(document).ready(function() {
  $("#example").DataTable({
    scrollY: "200px",
    scrollCollapse: true,
    paging: false
  });
});
```

`Scroll - horizontal`
```js
$(document).ready(function() {
  $("#example").DataTable({
    scrollX: true
  });
});
```

`DOM / jQuery events`
```js
$(document).ready(function() {
  var table = $("#example").DataTable();

  $("#example tbody").on("click", "tr", function() {
    var data = table.row(this).data();
    alert("You clicked on " + data[0] + "'s row");
  });
});
```

```js
$.extend(true, $.fn.dataTable.defaults, {
  searching: false,
  ordering: false
});

$(document).ready(function() {
  $("#example").DataTable();
});
```

`Add rows`
```js
$(document).ready(function() {
  var t = $("#example").DataTable();
  var counter = 1;

  $("#addRow").on("click", function() {
    t.row
      .add([
        counter + ".1",
        counter + ".2",
        counter + ".3",
        counter + ".4",
        counter + ".5"
      ])
      .draw(false);

    counter++;
  });

  // Automatically add a first row of data
  $("#addRow").click();
});
```


---

```html
<table id="myTable1" class="table table-striped table-bordered" cellspacing="0" width="100%">
  <thead>
    <tr>
      <th>Name</th>
      <th>Position</th>
      <th>Office</th>
      <th>Extn.</th>
      <th>Start date</th>
      <th>Salary</th>
    </tr>
  </thead>
</table>
<table id="myTable2" class="table table-striped table-bordered" cellspacing="0" width="100%">
  <thead>
    <tr>
      <th>Name</th>
      <th>Position</th>
      <th>Office</th>
      <th>Extn.</th>
      <th>Start date</th>
      <th>Salary</th>
    </tr>
  </thead>
</table>
```




---

```js
$("#example").dataTable({
  columnDefs: [
    {
      targets: 0,
      searchable: false
    }
  ]
});

var table = $("#myTable").DataTable({
  columnDefs: [
    { targets: [0, 1], visible: true },
    { targets: "_all", visible: false }
  ]
});

$(document).ready(function() {
  $("#example").DataTable({
    responsive: {
      details: false
    }
  });
});

$("#example").dataTable({
  columnDefs: [{ orderable: false, targets: 0 }]
});

$("#example").dataTable({
  columns: [{ orderable: false }, null, null, null, null]
});

var table = $("#example").DataTable({
  ajax: "../ajax/data/objects.txt",
  columns: [
    {
      className: "details-control",
      orderable: false,
      data: null,
      defaultContent: ""
    },
    { data: "name" },
    { data: "position" },
    { data: "office" },
    { data: "salary" }
  ],
  order: [[1, "asc"]]
});
```

#### :books: 參考網站：
- [columnDefs](https://datatables.net/reference/option/columnDefs)
- [columns.orderable](https://datatables.net/reference/option/columns.orderable)
- [disable-child-rows](https://datatables.net/extensions/responsive/examples/child-rows/disable-child-rows.html)
- [row_details](https://datatables.net/examples/api/row_details.html)
- [responsive](https://datatables.net/extensions/responsive/)

```js
var dataSet = [
    [ "Tiger Nixon", "System Architect", "Edinburgh", "5421", "2011/04/25", "$320,800" ],
    [ "Garrett Winters", "Accountant", "Tokyo", "8422", "2011/07/25", "$170,750" ],
    [ "Ashton Cox", "Junior Technical Author", "San Francisco", "1562", "2009/01/12", "$86,000" ],
    [ "Cedric Kelly", "Senior Javascript Developer", "Edinburgh", "6224", "2012/03/29", "$433,060" ],
    [ "Airi Satou", "Accountant", "Tokyo", "5407", "2008/11/28", "$162,700" ],
    [ "Brielle Williamson", "Integration Specialist", "New York", "4804", "2012/12/02", "$372,000" ],
    [ "Herrod Chandler", "Sales Assistant", "San Francisco", "9608", "2012/08/06", "$137,500" ],
    [ "Rhona Davidson", "Integration Specialist", "Tokyo", "6200", "2010/10/14", "$327,900" ],
    [ "Colleen Hurst", "Javascript Developer", "San Francisco", "2360", "2009/09/15", "$205,500" ],
    [ "Sonya Frost", "Software Engineer", "Edinburgh", "1667", "2008/12/13", "$103,600" ],
    [ "Jena Gaines", "Office Manager", "London", "3814", "2008/12/19", "$90,560" ],
    [ "Quinn Flynn", "Support Lead", "Edinburgh", "9497", "2013/03/03", "$342,000" ],
    [ "Charde Marshall", "Regional Director", "San Francisco", "6741", "2008/10/16", "$470,600" ],
    [ "Haley Kennedy", "Senior Marketing Designer", "London", "3597", "2012/12/18", "$313,500" ],
    [ "Tatyana Fitzpatrick", "Regional Director", "London", "1965", "2010/03/17", "$385,750" ],
    [ "Michael Silva", "Marketing Designer", "London", "1581", "2012/11/27", "$198,500" ],
    [ "Paul Byrd", "Chief Financial Officer (CFO)", "New York", "3059", "2010/06/09", "$725,000" ],
    [ "Gloria Little", "Systems Administrator", "New York", "1721", "2009/04/10", "$237,500" ],
    [ "Bradley Greer", "Software Engineer", "London", "2558", "2012/10/13", "$132,000" ],
    [ "Dai Rios", "Personnel Lead", "Edinburgh", "2290", "2012/09/26", "$217,500" ],
    [ "Jenette Caldwell", "Development Lead", "New York", "1937", "2011/09/03", "$345,000" ],
    [ "Yuri Berry", "Chief Marketing Officer (CMO)", "New York", "6154", "2009/06/25", "$675,000" ],
    [ "Caesar Vance", "Pre-Sales Support", "New York", "8330", "2011/12/12", "$106,450" ],
    [ "Doris Wilder", "Sales Assistant", "Sidney", "3023", "2010/09/20", "$85,600" ],
    [ "Angelica Ramos", "Chief Executive Officer (CEO)", "London", "5797", "2009/10/09", "$1,200,000" ],
    [ "Gavin Joyce", "Developer", "Edinburgh", "8822", "2010/12/22", "$92,575" ],
    [ "Jennifer Chang", "Regional Director", "Singapore", "9239", "2010/11/14", "$357,650" ],
    [ "Brenden Wagner", "Software Engineer", "San Francisco", "1314", "2011/06/07", "$206,850" ],
    [ "Fiona Green", "Chief Operating Officer (COO)", "San Francisco", "2947", "2010/03/11", "$850,000" ],
    [ "Shou Itou", "Regional Marketing", "Tokyo", "8899", "2011/08/14", "$163,000" ],
    [ "Michelle House", "Integration Specialist", "Sidney", "2769", "2011/06/02", "$95,400" ],
    [ "Suki Burks", "Developer", "London", "6832", "2009/10/22", "$114,500" ],
    [ "Prescott Bartlett", "Technical Author", "London", "3606", "2011/05/07", "$145,000" ],
    [ "Gavin Cortez", "Team Leader", "San Francisco", "2860", "2008/10/26", "$235,500" ],
    [ "Martena Mccray", "Post-Sales support", "Edinburgh", "8240", "2011/03/09", "$324,050" ],
    [ "Unity Butler", "Marketing Designer", "San Francisco", "5384", "2009/12/09", "$85,675" ]
];

$(document).ready(function() {
  $("#example").DataTable({
    data: dataSet,
    columns: [
      { title: "Name" },
      { title: "Position" },
      { title: "Office" },
      { title: "Extn." },
      { title: "Start date" },
      { title: "Salary" }
    ]
  });
});
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>jQuery demo</title>
  <script src="https://code.jquery.com/jquery-1.12.0.min.js"></script>
  <script src="https://cdn.datatables.net/1.10.11/js/jquery.dataTables.min.js"></script>
  <script src="https://cdn.datatables.net/1.10.11/js/dataTables.bootstrap.min.js"></script>

  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">
  <link rel="stylesheet" href="https://cdn.datatables.net/1.10.11/css/dataTables.bootstrap.min.css">
</head>
<body>
  <table id="example" class="display" width="100%"></table>
</body>
</html>
```

```
<link rel="stylesheet" href="https://cdn.datatables.net/1.10.11/css/jquery.dataTables.min.css">
```

#### :books: 參考網站：
- [datatables](https://datatables.net/)
- [theme-creator](https://datatables.net/manual/styling/theme-creator)
- [js_array](https://datatables.net/examples/data_sources/js_array.html)
- [bootstrap](https://datatables.net/examples/styling/bootstrap.html)

---

`objects_deep.txt`
```json
{
  "data": [{
    "name": "Tiger Nixon",
    "hr": {
      "position": "System Architect",
      "salary": "$320,800",
      "start_date": "2011\/04\/25"
    },
    "contact": [
      "Edinburgh",
      "5421"
    ]
  }, {
    "name": "Garrett Winters",
    "hr": {
      "position": "Accountant",
      "salary": "$170,750",
      "start_date": "2011\/07\/25"
    },
    "contact": [
      "Tokyo",
      "8422"
    ]
  }, {
    "name": "Donna Snider",
    "hr": {
      "position": "Customer Support",
      "salary": "$112,000",
      "start_date": "2011\/01\/25"
    },
    "contact": [
      "New York",
      "4226"
    ]
  }]
}
```

```js
function Employee(name, position, salary, office) {
  this.name = name;
  this.position = position;
  this.salary = salary;
  this._office = office;

  this.office = function() {
    return this._office;
  };
}

$("#example").DataTable({
  data: [
    new Employee("Tiger Nixon", "System Architect", "$3,120", "Edinburgh"),
    new Employee("Garrett Winters", "Director", "$5,300", "Edinburgh")
  ],
  columns: [
    { data: "name" },
    { data: "salary" },
    { data: "office" },
    { data: "position" }
  ]
});
```

#### :books: 參考網站：
- https://raw.githubusercontent.com/DataTables/DataTables/master/examples/ajax/data/objects_deep.txt


