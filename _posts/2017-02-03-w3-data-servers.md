---
layout: post
title: W3 Data Servers
date: 2017-02-03 17:14:00

---

```php
<?php
header("Access-Control-Allow-Origin: *");
header("Content-Type: application/json; charset=UTF-8");

$conn = new mysqli("myServer", "user", "pass","myDB");

$result = $conn->query("SELECT CompanyName, City, Country FROM Customers");

$outp = "";
while($rs = $result->fetch_array(MYSQLI_ASSOC)) {
    if ($outp != "") {$outp .= ",";}
    $outp .= '{"Name":"'  . $rs["CompanyName"] .'",';
    $outp .= '"City":"'   . $rs["City"]        .'",';
    $outp .= '"Country":"'. $rs["Country"]     .'"}'; 
}
$outp ='{"customers":['.$outp.']}';

$conn->close();

echo($outp);
?>
```

Node JS

```javascript
var express = require('express');
var app = express();

app.get('/', function (req, res) {
  var sql = require("mssql");
  var config = {user:'user', password:'pass', server:'myServer', database:'myDB'};
  sql.connect(config, function (err) {
    if (err) console.log(err);
    var request = new sql.Request();
    request.query('SELECT CompanyName, City, Country FROM Customers', function (err, recordset) {
      if (err) console.log(err)
      res.send(recordset);
    });
  });
});

var server = app.listen(5000, function () {
console.log('Server is running..');
});
```

ASP

```asp
@{
Response.AppendHeader("Access-Control-Allow-Origin","*")
Response.AppendHeader("Content-type","application/json")
var db = Database.Open("myDB");
var query = db.Query("SELECT CompanyName, City, Country FROM Customers");
var outp =""
var c = chr(34)
}

@foreach(var row in query)
{
if outp <> "" then outp = outp + ","
outp = outp + "{" + c + "Name"    + c + ":" + c + @row.CompanyName + c + ","
outp = outp +       c + "City"    + c + ":" + c + @row.City        + c + ","
outp = outp +       c + "Country" + c + ":" + c + @row.Country     + c + "}"
}
outp ="{" + c + "customers" + c + ":[" + outp + "]}"
@outp
```

PHP dan Access

```php
<?php
header("Access-Control-Allow-Origin: *");
header("Content-Type: application/json; charset=ISO-8859-1");

$conn = new COM("ADODB.Connection");
$conn->open("PROVIDER=Microsoft.Jet.OLEDB.4.0;Data Source=myDB.mdb");

$rs = $conn->execute("SELECT CompanyName, City, Country FROM Customers");

$outp = "";
while (!$rs->EOF) {
    if ($outp != "") {$outp .= ",";}
    $outp .= '{"Name":"'  . $rs["CompanyName"] .'",';
    $outp .= '"City":"'   . $rs["City"]        .'",';
    $outp .= '"Country":"'. $rs["Country"]     .'"}'; 
    $rs->MoveNext();
}
$outp ='{"customers":['.$outp.']}';

$conn->close();
echo ($outp);
?>
```

ASP dan Access

```asp
<%@ Import Namespace="System.IO"%>
<%@ Import Namespace="System.Data"%>
<%@ Import Namespace="System.Data.OleDb"%>

<%
Response.AppendHeader("Access-Control-Allow-Origin","*")
Response.AppendHeader("Content-type","application/json")

Dim conn As OleDbConnection
Dim objAdapter As OleDbDataAdapter
Dim objTable As DataTable
Dim objRow As DataRow
Dim objDataSet As New DataSet()
Dim outp
Dim c

conn = New OledbConnection("Provider=Microsoft.Jet.OLEDB.4.0;data source=myDB.mdb")
objAdapter = New OledbDataAdapter("SELECT CompanyName, City, Country FROM Customers", conn)
objAdapter.Fill(objDataSet, "myTable")
objTable=objDataSet.Tables("myTable")

outp = ""
c = chr(34)
for each x in objTable.Rows
if outp <> "" then outp = outp & ","
outp = outp & "{" & c & "Name"    & c & ":" & c & x("CompanyName") & c & ","
outp = outp &       c & "City"    & c & ":" & c & x("City")        & c & ","
outp = outp &       c & "Country" & c & ":" & c & x("Country")     & c & "}"
next
outp ="{" & c & "customers" & c & ":[" & outp & "]}"

conn.close
response.write(outp)
%>
```
