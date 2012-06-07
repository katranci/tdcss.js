tdcss.js - Test-driven CSS development
================

A very small framework for structured/TDD-style HTML/CSS development.

Write solid and reusable code by styling design elements in isolation.

What's the benefit
---
tdcss.js was inspired by the modular approach of Object-oriented CSS (<http://oocss.org>) and SMACSS (<http://smacss.com>).

It's especially well suited for using these techniques to model up style tiles (<http://styletil.es/>) in frontend code.


How to use
---

In the header, insert a reference to jQuery and tdcss.js, then apply $.tdcss() on the container holding your fragments:
```html
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.2/jquery.min.js"></script>
<script type="text/javascript" src="src/tdcss.js"></script>
<script type="text/javascript">
     $(function(){
         $("#my-fragments").tdcss();
     })
</script>
```

Also, you need to reference the stylesheet(s) that you will be testing:
```html
<!-- Project CSS -->
<link rel="stylesheet" href="demo/style.css" type="text/css" media="screen">
```

Inside a div with the id #tdcss, insert an html comment with the text "###" to denote a fragment:
```html
<!-- ### -->
```

The first text after the prefix becomes the title of the fragment:
```html
<!-- ### Element title -->
```

Then, if you insert a semi-colon, you can specify which **section** the fragment belongs to:
```html
<!-- ### Element title; Title styles -->
```

And finally, if you insert another semicolon, you can fix the height of the fragment container.
This is useful for position:absolute type layouts that don't by themselfes force the container to expand:
```html
<!-- ### Element title; Title styles; 400px -->
```

Here's the markup that produces the screenshot below:
```html
<div id="tdcss">

<!-- ### Demo element -->
<div class="some-structure">
    <p>This is a demo element.</p>
</div>

<!-- ### Another demo element -->
<a href="#">This is a demo link.</a>


<!-- ### H1; typography -->
<h1>This is a test.</h1>

<!-- ### H2; typography -->
<h2>This is a test.</h2>

<!-- ### H3; typography -->
<h3>This is a test.</h3>


<!-- ### Some element that needs a lot of space; Custom height; 500px -->
<h3>This is a test.</h3>

</div>
```

tdcss.js will interpret the comments and present your design elements in a nice, structured way.
The point is to help you make your design elements context independent.


![How it looks](https://github.com/jakobloekke/tdcss.js/raw/master/demo/preview.png)

Todo
---
Make a better looking demo + screenshot! :)