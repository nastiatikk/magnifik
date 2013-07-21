---
layout: base
title: Mobify.js Magnifik Module Examples
description:
    See examples of the Mobify.js expanding bellows module in action,
    including the sample code snippets.
---

<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
<script src="//code.jquery.com/jquery-1.10.1.js"></script>
<script src="//cdn.mobify.com/modules/magnifik/0.1.0/magnifik.min.js"></script>


<style>
.corner.m-close { color: white; background: black; position: absolute; right: 0; top: 0;
    font-weight: bold; font-size: 18px; padding: 10px;
}
.magnifik-notice {
    position: absolute; left: 50%; top: 50%;
    width: 300px; height: 36px; margin-left: -160px; margin-top: -28px; padding: 10px;
    vertical-align: middle; text-align: center; font-weight: bold; font-size: 16px; line-height: 18px;
    background: rgba(0,0,192,0.5); color: white; 
    opacity: 1;
}
.magnifik-notice-fade {
    -webkit-transition: opacity 4s ease-in; 
    -o-transition: opacity 4s ease-in; 
    -moz-transition: opacity 4s ease-in; 
    -ms-transition: opacity 4s ease-in; 
    transition: opacity 4s ease-in;
    opacity: 0;
 }
a img { width: 100%; }
.z4-wrap { height: 300px; border: 3px solid black; }
</style>


<h2>Basic Magnifik</h2>
<a class="z1" href="//www.fillmurray.com/g/400/600"><img src="//www.fillmurray.com/g/400/600"></a>
<script>$('a.z1').magnifik();</script>

<h3>Code for this example:</h3>
<pre><code>&lt;a class=&quot;z1&quot; href=&quot;//www.fillmurray.com/g/400/600&quot;&gt;&lt;img src=&quot;//www.fillmurray.com/g/400/600&quot;&gt;&lt;/a&gt;
&lt;script&gt;$('a.z1').magnifik();&lt;/script&gt;</code></pre>

<h2>With a textual 'zoom in' link and closing only via Close button</h2>
<a class="z2" href="//www.fillmurray.com/g/400/600"><img src="//www.fillmurray.com/g/400/600">Zoom in</a>
<script>
$('a.z2').magnifik({
    clickCloses: false,
    stageHTML: function() {
        return Mobify.UI.Magnifik.defaults.stageHTML.call(this) + '<div class="m-close corner">Close</div>';
    }
});
</script>

<h3>Code for this example:</h3>
<pre><code>&lt;a class=&quot;z2&quot; href=&quot;//www.fillmurray.com/g/400/600&quot;&gt;&lt;img src=&quot;//www.fillmurray.com/g/400/600&quot;&gt;Zoom in&lt;/a&gt;
&lt;script&gt;
$('a.z2').magnifik({
    clickCloses: false,
    stageHTML: function() {
        return Mobify.UI.Magnifik.defaults.stageHTML.call(this) + '&lt;div class=&quot;m-close corner&quot;&gt;Close&lt;/div&gt;';
    }
});
&lt;/script&gt;</code></pre>

<h2>Messaging upon opening</h2>
<a class="z3" href="//www.fillmurray.com/g/400/600"><img src="//www.fillmurray.com/g/400/600"></a>
<script>
$('a.z3').magnifik({
    stageHTML: function() {
      return Mobify.UI.Magnifik.defaults.stageHTML.call(this)
          + '<div class="magnifik-notice m-close">Tap anywhere to close. On touchscreen device, drag to navigate</div>';
    }
}).bind('afterOpen.magnifik', function() {
  $('.magnifik-notice').addClass('magnifik-notice-fade');
}).bind('beforeClose.magnifik', function() {
  $('.magnifik-notice').removeClass('magnifik-notice-fade');
});
</script>

<h3>Code for this example:</h3>
<pre><code>&lt;a class=&quot;z3&quot; href=&quot;//www.fillmurray.com/g/400/600&quot;&gt;&lt;img src=&quot;//www.fillmurray.com/g/400/600&quot;&gt;&lt;/a&gt;
&lt;script&gt;
$('a.z3').magnifik({
    stageHTML: function() {
      return Mobify.UI.Magnifik.defaults.stageHTML.call(this)
          + '&lt;div class=&quot;magnifik-notice m-close&quot;&gt;Tap anywhere to close. On touchscreen device, drag to navigate&lt;/div&gt;';
    }
}).bind('afterOpen.magnifik', function() {
  $('.magnifik-notice').addClass('magnifik-notice-fade');
}).bind('beforeClose.magnifik', function() {
  $('.magnifik-notice').removeClass('magnifik-notice-fade');
});
&lt;/script&gt;</code></pre>

<h2>Limiting magnifik to a container</h2>
<a class="z4" href="//www.fillmurray.com/g/400/600"><img src="//www.fillmurray.com/g/400/600"></a>
<div class="z4-wrap"></div>
<script>
    $('a.z4').magnifik({stage: '.z4-wrap'});
</script>

<h3>Code for this example:</h3>
<pre><code>&lt;a class=&quot;z4&quot; href=&quot;//www.fillmurray.com/g/400/600&quot;&gt;&lt;img src=&quot;//www.fillmurray.com/g/400/600&quot;&gt;&lt;/a&gt;
&lt;div class=&quot;z4-wrap&quot;&gt;&lt;/div&gt;
&lt;script&gt;
    $('a.z4').magnifik({stage: '.z4-wrap'});
&lt;/script&gt;</code></pre>
