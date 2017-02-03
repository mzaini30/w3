---
layout: post
title: W3 Data Controllers
date: 2017-02-03 17:43:00

---

```javascript
// Add a controller to modify data before display
myController();

w3DisplayData("id01", myObject);
```

Convert to Uppercase

```javascript
function myController() {
  var i, x;
  var myArray = myObject["cd"];
  for (i = 0; i < myArray.length; i++) {
    myArray[i]["CustomerName"] =
    myArray[i]["CustomerName"].toUpperCase();
  }
}
```

Summarize Price

```javascript
function myController() {
  var i;
  var x;
  var total = 0;
  var myArray = myObject["cd"];
  for (i = 0; i < myArray.length; i++) {
    total += Number(myArray[i]["price"]);
  }
  myObject["total"] = total.toFixed(2);
}
```
