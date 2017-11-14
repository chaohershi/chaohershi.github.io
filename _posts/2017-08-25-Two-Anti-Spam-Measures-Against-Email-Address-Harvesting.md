---
title: Two Anti-Spam Measures Against Email Address Harvesting
---

Let's say we want to obfuscate the following mailto link:

`<a href="mailto:example@email.com">Send a message</a>`

## Go for ASCII
```
<&#97;&#32;&#104;&#114;&#101;&#102;&#61;&#34;&#109;&#97;&#105;&#108;&#116;&#111;&#58;&#101;&#120;&#97;&#109;&#112;&#108;&#101;&#64;&#101;&#109;&#97;&#105;&#108;&#46;&#99;&#111;&#109;&#34;&#62;&#83;&#101;&#110;&#100;&#32;&#97;&#32;&#109;&#101;&#115;&#115;&#97;&#103;&#101;&#60;&#47;&#97;>
```

## Encode with JavaScript
Basic version:
```javascript
<script type="text/javascript">
  var username = "example";
  var hostname = "email.com";
  document.write("<a href='mailto:" + username + "@" + hostname + "'>Send a message</a>");
</script>
```

A cooler version using [ROT13](https://en.wikipedia.org/wiki/ROT13) alogrithm:
```javascript
<script type="text/javascript">document.write("<n uers="znvygb:rknzcyr@rznvy.pbz">Fraq n zrffntr</n>".replace(/[a-zA-Z]/g, 
  function(c){return String.fromCharCode((c<="Z"?90:122)>=(c=c.charCodeAt(0)+13)?c:c-26);}));
</script>
```
