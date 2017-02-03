---
layout: post
title: W3 Data Objects
date: 2017-02-03 19:26:00

---

```javascript
var myObject = {"customers":[
{"CustomerName":"Alfreds Futterkiste","City":"Berlin","Country":"Germany"},
{"CustomerName":"Around the Horn","City":"London","Country":"UK"},
{"CustomerName":"B's Beverages","City":"London","Country":"UK"},
{"CustomerName":"Blauer See Delikatessen","City":"Mannheim","Country":"Germany"},
{"CustomerName":"Bon app'","City":"Marseille","Country":"France"},
{"CustomerName":"Bottom-Dollar Marketse","City":"Tsawassen","Country":"Canada"},
{"CustomerName":"Chop-suey Chinese","City":"Bern","Country":"Switzerland"}
]};
```

Filling a Dropdown

```html
<select id="id01">
<option w3-repeat="customers">{{CustomerName}}</option>
</select>

<script>
w3DisplayData("id01", myObject);
</script>
```

Filling a List

```html
<ul id="id01">
  <li w3-repeat="customers">{{CustomerName}}</li>
</ul>

<script>
w3DisplayData("id01", myObject);
</script>
```

Filling Check Boxes

```html
<table id="id01">
  <tr w3-repeat="customers" class="{{Color}}">
    <td>{{CustomerName}}</td>
    <td><input type="checkbox" {{checked}}"></td>
  </tr>
</table>

<script>
w3DisplayData("id01", myObject);
</script> 
```

Filling Classes

```html
<table id="id01">
  <tr w3-repeat="customers" class="{{Color}}">
    <td>{{CustomerName}}</td>
  </tr>
</table>

<script>
w3DisplayData("id01", myObject);
</script>
```

```html
<table id="id01">
  <tr w3-repeat="customers" class="{{Size}}">
    <td>{{CustomerName}}</td>
  </tr>
</table>

<script>
w3DisplayData("id01", myObject);
</script> 
```

Filling a Table

```html
<table id="id01">
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
w3DisplayData("id01", myObject);
</script>
```
