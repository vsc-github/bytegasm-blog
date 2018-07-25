---
title: Make entire text on the page editable
subTitle: a look at contentEditable property
category: "short bytes"
cover: editable.png
---

#Making div, p, span, etc editable on a webapage 

Before taking a look at how to do it, let us first take a look at the why would we want to do it.

## Use Cases:

+ To try out different text in Headlines and Buttons without having to make changes to the code.
+ To make changes to the fields on the page when you want to take a screenshot of the said webpage.
+ For  making rich text editors. eg WYSIWYG editors.
+ Just for fun.

## How to:
Passing a `contenteditable="true"` attribute to HTML elements make them editable.
Yes, it's as simple as that.
```
<p contenteditable="true">
  This is an editable paragraph.
</p>
```
[Play with above code here.](https://codepen.io/bantic/pen/BNgvKa)

**Note:** You can apply this attribute to almost any HTML element and  it'll make the text inside the element editable.


## What if I put contenteditable on body tag?
Yes you can and you should if you want the entire page to be editable. 

There's also a nifty way to do it on the fly and to any webpage: 

  1. Open developers tools in the browser. (right-click -> inspect element)
  2. Navigate to the console tab.
  3. Type `document.body.contentEditable = true`.
  4. Now you can just click on any text on the webpage and edit it.

**Demo:**
I have put a nice working demo and a short post about this topic on my instagram [ByteGasm](https://www.instagram.com/p/BlkzuaPBd8R/). Check it out. There's some other great posts over there too.

##More Sauce

+ [ContentEditable Attirbute on MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contenteditable)
+ [Developing a WYSIWYG editor using contentEditable](https://medium.com/content-uneditable/contenteditable-the-good-the-bad-and-the-ugly-261a38555e9c)
+ [Content Uneditable Blog](https://medium.com/content-uneditable)
