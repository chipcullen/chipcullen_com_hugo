---
title: "Iframe"
date: Sun, 01 Nov 2020 16:00:46 +0000
draft: false
layout: "page"
---

## I'm an iframe

<script>
  console.log('coming from the iframe');
  console.log(`the document referrer is ${document.referrer}`);
  document.cookie = "c_is_for=cookies;";

  var getCookie = function (name) {
    var value = "; " + document.cookie;
    var parts = value.split("; " + name + "=");
    if (parts.length == 2) return parts.pop().split(";").shift();
  };

// Example
var cookieVal = getCookie('c_is_for'); // returns "turkey"
console.log(cookieVal);
  </script>
