---
layout: post
title: W3 Data References
date: 2017-02-03 14:13:00

---

```html
<!DOCTYPE html>
<html>
<script src="http://www.w3schools.com/lib/w3data.js"></script>
<body>

<div id="id01">
{{firstName}} {{lastName}}
</div>

<script>
w3DisplayData("id01", {"firstName" : "John","lastName" : "Doe"});
</script>

</body>
</html> 
```

```html
<!DOCTYPE html>
<html>
<link rel="stylesheet"href="http://www.w3schools.com/lib/w3.css">
<script src="http://www.w3schools.com/lib/w3data.js"></script>
<body>

<table id="id01" class="w3-table w3-bordered w3-striped">
  <tr>
    <th>Customer</th>
    <th>City</th>
    <th>Country</th>
  </tr>
  <tr w3-repeat="customers">
    <td>{{CustomerName}}</td>
    <td>{{City}}</td>
    <td>{{Country}}</td>
  </tr>
</table>

<script>
w3Http("customers.php", function () {
  if (this.readyState == 4 && this.status == 200) {
    var myObject = JSON.parse(this.responseText);
    w3DisplayData("id01", myObject);
  }
});
</script>

</body>
</html> 
```

```html
<!DOCTYPE html>
<html>
<script src="http://www.w3schools.com/lib/w3data.js"></script>
<body>

<div w3-include-HTML="h1.html"></div>
<div w3-include-HTML="content.html"></div>

<script>
w3IncludeHTML();
</script>

</body>
<html>
```
