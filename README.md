Shorten
=======

![jquery shorten plugin](http://img.viralpatel.net/2010/12/show-more-link.png "jquery shorten plugin")

A simple jquery plugin that automatically shortens text within an element, honoring HTML tags and add "more" link.

This Fork moved the More link into the same line as the text, to save even more space and to add a nice fade out 
effect and to match some respnsiveness requirements.

*Read tutorial: [jQuery Shorten](http://viralpatel.net/blogs/dynamically-shortened-text-show-more-link-jquery/).*

Usage
-----
Shortens the text within 'element' and add a 'more' link.

    $(element).shorten();

Add a link with text 'read more' while shortening the content of element.

	$(element).shorten({
		moreText: 'read more'
	});

Change the link text to 'read more' and 'read less' overriding default value 'more' and 'less'.

	$(element).shorten({
		moreText: 'read more',
		lessText: 'read less'
	});

Override default display 100 characters and hide text above 50 characters.

	$(element).shorten({
		showChars: 50,
	});

To add a fadeout effect add following styles to your css:

    .ellip {
      position: relative;
      margin: 0 10px 0 0;
    }

    .ellip::before {
      content: '';
      display: inline-block;
      position: absolute;
      left: -37px;
      width: 37px;
      height: 20px;
      background: rgba(255, 255, 255, 0);
      background: -moz-linear-gradient(left, rgba(255, 255, 255, 0) 0%, rgba(255, 255, 255, 0.66) 66%, rgba(255, 255, 255, 1) 100%);
      background: -webkit-linear-gradient(left, rgba(255, 255, 255, 0) 0%, rgba(255, 255, 255, 0.66) 66%, rgba(255, 255, 255, 1) 100%);
      background: -o-linear-gradient(left, rgba(255, 255, 255, 0) 0%, rgba(255, 255, 255, 0.66) 66%, rgba(255, 255, 255, 1) 100%);
      background: -ms-linear-gradient(left, rgba(255, 255, 255, 0) 0%, rgba(255, 255, 255, 0.66) 66%, rgba(255, 255, 255, 1) 100%);
      background: linear-gradient(to right, rgba(255, 255, 255, 0) 0%, rgba(255, 255, 255, 0.66) 66%, rgba(255, 255, 255, 1) 100%);
      filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#ffffff', endColorstr='#ffffff', GradientType=1);
    }

Known-Issues
------------
When the cut of the long text happens inside a html tag, then the 'Read more' text is inside this tag. See **samples/index.html** for a demo. Inside a-tags this can lead to problems, so be aware of your content.

Parameters
----------
You can change the behaviour by changing following js variables.

| Property       | Description                                                                               |
| -------------- | ----------------------------------------------------------------------------------------- |
| `showChars`    | Total characters to show to user. If the content is more then showChar, it will be split into two halves and first one will be showed to user. |
| `ellipsesText` | The text displayed before “more” link. Default is “…”                                     |
| `moreText`     | The text shown in more link. Default is “more”. You can change to ">>" or "read more"     |
| `lessText`     | The text shown in less link. Default is “less”. You can change to "<<" or "read less"     |
| `onMore`       | Callback function to trigger when "more" is clicked                                       |
| `onLess`       | Callback function to trigger when "less" is clicked                                       |


Licence
-------

	Copyright 2013 Viral Patel and other contributors
	http://viralpatel.net

	Permission is hereby granted, free of charge, to any person obtaining
	a copy of this software and associated documentation files (the
	"Software"), to deal in the Software without restriction, including
	without limitation the rights to use, copy, modify, merge, publish,
	distribute, sublicense, and/or sell copies of the Software, and to
	permit persons to whom the Software is furnished to do so, subject to
	the following conditions:

	The above copyright notice and this permission notice shall be
	included in all copies or substantial portions of the Software.

	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
	EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
	MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
	NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
	LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
	OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
	WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
