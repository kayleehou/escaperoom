---
title: Searchbar
layout: default
tags: [API]
permalink: searchbar
---

<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body {
  font-family: Arial, Helvetica, sans-serif;
}

* {
  box-sizing: border-box;
}

/* Create a column layout with Flexbox */
.row {
  display: flex;
}

/* Left column (menu) */
.left {
  flex: 35%;
  padding: 15px 0;
}

.left h2 {
  padding-left: 8px;
}

/* Right column (page content) */
.right {
  flex: 65%;
  padding: 15px;
}

/* Style the search box */
#mySearch {
  width: 100%;
  font-size: 18px;
  padding: 11px;
  border: 1px solid #ddd;
}

/* Style the navigation menu inside the left column */
#myMenu {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

#myMenu li a {
  padding: 12px;
  text-decoration: none;
  color: black;
  display: block
}

#myMenu li a:hover {
  background-color: #2d2e2e;
}
</style>
</head>
<body>

<h1 style="font-family:'Courier New'; text-align:center; font-size: 50px">Marvel Searchbar</h1>
<p style="font-family:'Courier New'; text-align:center; font-size: 18px">Start to type for a specific Marvel comic or character inside the search bar to "filter" the search options.</p>

<div class="row">
  <div class="left" style="background-color:#4f5359;">
    <h2>Menu</h2>
    <input type="text" id="mySearch" onkeyup="myFunction()" placeholder="Search.." title="Type in a category">
    <ul id="myMenu">
      <li><a href="#">Iron Man</a></li>
      <li><a href="#">Spider Man</a></li>
      <li><a href="#">Thor</a></li>
      <li><a href="#">Loki</a></li>
      <li><a href="#">Black Widow</a></li>
      <li><a href="#">Scarlet Witch</a></li>
      <li><a href="#">Dr. Strange</a></li>
      <li><a href="#">Ant Man</a></li>
    </ul>
  </div>
  
  <div class="right" style="background-color:#4f5359;">
    <h2>Learn More!</h2>
    <p>Over here we'll share any comics with that character or comics similar to the one you searched. </p>
  </div>
</div>

<script>
function myFunction() {
  var input, filter, ul, li, a, i;
  input = document.getElementById("mySearch");
  filter = input.value.toUpperCase();
  ul = document.getElementById("myMenu");
  li = ul.getElementsByTagName("li");
  for (i = 0; i < li.length; i++) {
    a = li[i].getElementsByTagName("a")[0];
    if (a.innerHTML.toUpperCase().indexOf(filter) > -1) {
      li[i].style.display = "";
    } else {
      li[i].style.display = "none";
    }
  }
}
</script>

</body>
</html>
