---
layout: post
title: W3 CSS Slideshow
date: 2017-02-04 09:20:00

---

{::nomarkdown}
<h2 class="w3-center">Manual Slideshow</h2>
<div class="w3-content w3-display-container">
	<img class="mySlides" src="http://muhammadzaini.com/gambar/w3/img_fjords.jpg" style="width:100%"> <img class="mySlides" src="http://muhammadzaini.com/gambar/w3/img_lights.jpg" style="width:100%"> <img class="mySlides" src="http://muhammadzaini.com/gambar/w3/img_mountains.jpg" style="width:100%"> <img class="mySlides" src="http://muhammadzaini.com/gambar/w3/img_forest.jpg" style="width:100%"> <a class="w3-btn-floating w3-display-left" onclick="plusDivs(-1)">&#10094;</a> <a class="w3-btn-floating w3-display-right" onclick="plusDivs(1)">&#10095;</a>
</div>
<script>
var slideIndex = 1;
showDivs(slideIndex);

function plusDivs(n) {
  showDivs(slideIndex += n);
}

function showDivs(n) {
  var i;
  var x = document.getElementsByClassName("mySlides");
  if (n > x.length) {slideIndex = 1}    
  if (n < 1) {slideIndex = x.length}
  for (i = 0; i < x.length; i++) {
     x[i].style.display = "none";  
  }
  x[slideIndex-1].style.display = "block";  
}
</script>
{:/}

```html
<h2 class="w3-center">Manual Slideshow</h2>
<div class="w3-content w3-display-container">
	<img class="mySlides" src="http://muhammadzaini.com/gambar/w3/img_fjords.jpg" style="width:100%"> <img class="mySlides" src="http://muhammadzaini.com/gambar/w3/img_lights.jpg" style="width:100%"> <img class="mySlides" src="http://muhammadzaini.com/gambar/w3/img_mountains.jpg" style="width:100%"> <img class="mySlides" src="http://muhammadzaini.com/gambar/w3/img_forest.jpg" style="width:100%"> <a class="w3-btn-floating w3-display-left" onclick="plusDivs(-1)">&#10094;</a> <a class="w3-btn-floating w3-display-right" onclick="plusDivs(1)">&#10095;</a>
</div>
<script>
var slideIndex = 1;
showDivs(slideIndex);

function plusDivs(n) {
  showDivs(slideIndex += n);
}

function showDivs(n) {
  var i;
  var x = document.getElementsByClassName("mySlides");
  if (n > x.length) {slideIndex = 1}    
  if (n < 1) {slideIndex = x.length}
  for (i = 0; i < x.length; i++) {
     x[i].style.display = "none";  
  }
  x[slideIndex-1].style.display = "block";  
}
</script>
```
