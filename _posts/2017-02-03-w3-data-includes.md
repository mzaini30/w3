---
layout: post
title: W3 Data Includes
date: 2017-02-03 17:48:00

---

content.html

```html
<a href="http://www.w3schools.com/html/">HTML</a><br>
<a href="http://www.w3schools.com/css/">CSS</a><br>
<ahref="http://www.w3schools.com/bootstrap/">Bootstrap</a><br>
<ahref="http://www.w3schools.com/js/">JavaScript</a><br>
<a href="http://www.w3schools.com/sql/">SQL</a><br>
<a href="http://www.w3schools.com/php/">PHP</a><br>
<a href="http://www.w3schools.com/w3css/">W3.CSS</a><br>
```

```html
<div w3-include-html="content.html"></div>
```

```html
<script>
w3IncludeHTML();
</script>
```

```html
<!DOCTYPE html>
<html>
<scriptsrc="http://www.w3schools.com/lib/w3data.js"></script>
<body>

<div w3-include-html="content.html"></div>

<script>
w3IncludeHTML();
</script>

</body>
</html>
```

```html
<!DOCTYPE html>
<html>
<scriptsrc="http://www.w3schools.com/lib/w3data.js"></script>
<body>

<div w3-include-HTML="h1.html"></div>
<div w3-include-HTML="content.html"></div>

<script>
w3IncludeHTML();
</script>

</body>
<html>
```
