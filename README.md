LiteBox v1.3
============

A versatile, auto detecting content, lightbox/modal window for use with images, embedded content (YouTube, Vimeo, Daily Motion and KickStarter), iframes and inline html.

**Demo:** http://www.cloud-eight.com/github/litebox/


Usage
=====

Link both the 'litebox.css', 'images-loaded.js' and 'litebox.js' files into your document.

Simply place the link to the content in a hyperlinks `href` attribute, give it a class name which you will then use to call LiteBox.

```
<a href="001.jpg" target="_self" class="litebox"><img src="001-thumb.jpg" alt="Image 001" /></a>
```

For embedded content, you only need the URL to the page, not the embed code they provide, as the script will dynamically create the correct link to fetch the video.

```
<a href="https://www.youtube.com/watch?v=[token-id]" target="_self" class="litebox">YouTube</a>
<a href="https://www.youtu.be/[token-id]" target="_self" class="litebox">YouTube (Alt)</a>
<a href="http://vimeo.com/[token-id]" target="_self" class="litebox">Vimeo</a>
<a href="http://www.dailymotion.com/video/[token-id]" target="_self" class="litebox">Daily Motion</a>
<a href="https://www.kickstarter.com/projects/[token-id]/[token-name]/" target="_self" class="litebox">KickStarter</a>
```

To place a website in an iframe, just link to that particular page as you would do any other hyperlink.
For inline content, create the element somewhere on your page, set its display to none, within there create your element and give it an unique id. Then place this id (with the hashtag) in the `href` attributes value.

```
<a href="http://www.bing.com" target="_self" class="litebox">Iframe</a>
<a href="#inline-html-1" target="_self" class="litebox">Inline HTML </a>

<div style="display: none;">
	<div id="inline-html-1">
		<h1 class="bm-large tm-large">Inline HTML Example</h1>
		<p class="bm-large">In here you can pull any elements from the page to display in the Litebox</p>
	</div>
</div>
```

You can also create a gallery/group where you can navigate through the content by adding the attribute `data-litebox-group`, this works for any type of content and can even have mixed content.

```
<a href="001.jpg" target="_self" class="litebox" data-litebox-group="group-1"><img src="001-thumb.jpg" alt="Image 001" /></a>
<a href="002.jpg" target="_self" class="litebox" data-litebox-group="group-1"><img src="002-thumb.jpg" alt="Image 002" /></a>
<a href="003.jpg" target="_self" class="litebox" data-litebox-group="group-1"><img src="003-thumb.jpg" alt="Image 003" /></a>
<a href="004.jpg" target="_self" class="litebox" data-litebox-group="group-1"><img src="004-thumb.jpg" alt="Image 004" /></a>
```

To add a text or caption to the overlay, use the `data-litebox-text` attribute.

```
<a href="001.jpg" target="_self" class="litebox" data-litebox-text="Image 001"><img src="001-thumb.jpg" alt="Image 001" /></a>
```

To call the plugin and set options:

```
$('.litebox').liteBox({
  revealSpeed: 400,
  background: 'rgba(0,0,0,.8)',
  overlayClose: true,
  escKey: true,
  navKey: true,
  callbackInit: function() {},
  callbackBeforeOpen: function() {},
  callbackAfterOpen: function() {},
  callbackBeforeClose: function() {},
  callbackAfterClose: function() {},
  callbackError: function() {},
  callbackPrev: function() {},
  callbackNext: function() {},
  errorMessage: 'Error loading content.'
});
```


Options
=======

| Options             | Default                  | Description |
|:--------------------|:-------------------------|:------------|
| revealSpeed         | 400                      | The fade in time of the lightbox |
| background          | 'rgba(0, 0, 0, .8)'      | Sets the background color of the dimmer that overlays the viewport. |
| overlayClose        | true                     | When set to true, clicking the overlay will close the lightbox. |
| escKey              | true                     | When set to true, pressing the Esc key will close the lightbox. |
| navKey              | true                     | When set to true, pressing the Left or Right arrow keys will navigation through any grouped content in the lightbox |
| callbackInit        | function() {}            | Calls a JavaScript function when the lightbox is initiated. |
| callbackBeforeOpen  | function() {}            | Calls a JavaScript function before the lightbox is opened. |
| callbackAfterOpen   | function() {}            | Calls a JavaScript function after the lightbox is opened. |
| callbackBeforeClose | function() {}            | Calls a JavaScript function before the lightbox is closed. |
| callbackAfterClose  | function() {}            | Calls a JavaScript function after the lightbox is closed. |
| callbackError       | function() {}            | Calls a JavaScript function when the lightbox encounters an error. |
| callbackPrev        | function() {}            | Calls a JavaScript function when the prev button of the lightbox is triggered. |
| callbackNext        | function() {}            | Calls a JavaScript function when the next button of the lightbox is triggered. |
| errorMessage        | 'Error loading content.' | Sets the error message that is displayed upon the plugin encountering an error. |


Browser Compatibility
=====================

<ul>
  <li>IE 8+</li>
  <li>Firefox</li>
  <li>Chrome</li>
  <li>Safari</li>
  <li>Opera</li>
  <li>Most mobile browsers</li>
</ul>


Author
======

Joe Mottershaw, Cloud Eight<br />
http://www.cloud-eight.com


Credits
======

imagesLoaded, David DeSandro<br />
https://github.com/desandro/imagesloaded

tipsy, Jason Frame<br />
https://github.com/jaz303/tipsy