# Ti.SvgView Module

## Description

This module simply create a view from an svg file by exposing the androidsvg-1.2.1 lib and the SVGKit 2.X for IOS lib.

## Quick Start

### Get it [![gitTio](http://gitt.io/badge.png)](http://gitt.io/component/com.geraudbourdin.svgview)
Download the latest distribution ZIP-file and consult the [Titanium Documentation](http://docs.appcelerator.com/titanium/latest/#!/guide/Using_a_Module) on how install it, or simply use the [gitTio CLI](http://gitt.io/cli):

`$ gittio install com.geraudbourdin.svgview`

## Usage :

```javascript
var win = Ti.UI.createWindow({
	backgroundColor: "#fff"
});

var svgView = require('com.geraudbourdin.svgview');
var svg1 = svgView.createView({
	image: "/test.svg",
	width: 350,
	height: 350,
	top: 0,
	left: 0
});

if (OS_ANDROID) {
    var svg2 = svgView.createView({
    	image: '<svg width="30" height="30" viewBox="0 0 30 30" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"><g id="Symbols" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd"><g id="ICON/c-select-gb" fill-rule="nonzero"><g id="united-kingdom"><circle id="Oval" fill="#f0f0f0" cx="15" cy="15" r="15"/><g id="Group" transform="translate(0.468750, 0.468750)" fill="#0052b4"><path d="M2.63203125 5.39894531C1.45376953 6.93193359.5653125 8.69882812.0479882813 10.6183008H7.85138672L2.63203125 5.39894531z" id="Shape"/><path d="M29.0145117 10.6183008C28.4971875 8.69888672 27.6086719 6.93199219 26.4304687 5.39900391L21.2112305 10.6183008H29.0145117z" id="Shape"/><path d="M.0479882813 18.444375C.565371094 20.3637891 1.45382812 22.1306836 2.63203125 23.6636133L7.85121094 18.444375H.0479882813z" id="Shape"/><path d="M23.6635547 2.63208984C22.1305664 1.45382812 20.3637305.565371094 18.4442578.0479882813V7.85132812l5.2192969-5.21923828z" id="Shape"/><path d="M5.39894531 26.4304102C6.93193359 27.6086719 8.69882813 28.4971289 10.6182422 29.0145117V21.2112305L5.39894531 26.4304102z" id="Shape"/><path d="M10.6181836.0479882813C8.69876953.565371094 6.931875 1.45382812 5.39894531 2.63203125L10.6181836 7.85126953V.0479882813z" id="Shape"/><path d="M18.4443164 29.0145117C20.3637305 28.4971289 22.130625 27.6086719 23.6635547 26.4304687L18.4443164 21.2112305V29.0145117z" id="Shape"/><path d="M21.2112305 18.444375 26.4304687 23.6636719C27.6086719 22.1307422 28.4971875 20.3637891 29.0145117 18.444375H21.2112305z" id="Shape"/></g><g id="Group" fill="#d80027"><path d="M29.8730273 13.0434961H16.9566211 16.9565625V.126972656C16.3160742.04359375 15.6631055.0 15 0 14.3367773.0 13.6839258.04359375 13.0434961.126972656V13.0433789 13.0434375H.126972656C.04359375 13.6839258.0 14.3368945.0 15 0 15.6632227.04359375 16.3160742.126972656 16.9565039H13.0433789 13.0434375V29.8730273C13.6839258 29.9564062 14.3367773 30 15 30 15.6631055 30 16.3160742 29.9564648 16.9565039 29.8730273V16.9566211 16.9565625H29.8730273C29.9564062 16.3160742 30 15.6632227 30 15 30 14.3368945 29.9564062 13.6839258 29.8730273 13.0434961z" id="Shape"/><path d="M18.9130664 18.9130664 25.606582 25.6066406C25.9144336 25.2989063 26.2081055 24.977168 26.4883008 24.6436523L20.7577148 18.9130664H18.9130664z" id="Shape"/><path d="M11.0869336 18.913125H11.0868164L4.39335938 25.606582C4.70109375 25.9144336 5.02283203 26.2081055 5.35634766 26.4883008L11.0869336 20.7575977V18.913125z" id="Shape"/><path d="M11.0869336 11.0870508V11.0869336L4.39341797 4.39335938C4.08556641 4.70109375 3.79189453 5.02283203 3.51169922 5.35634766L9.24234375 11.0869922 11.0869336 11.0870508z" id="Shape"/><path d="M18.9130664 11.0870508 25.6066406 4.39341797C25.2989063 4.08556641 24.977168 3.79189453 24.6436523 3.51175781L18.9130664 9.24240234V11.0870508z" id="Shape"/></g></g></g></g></svg>',
    	width: 100,
    	height: 100,
    	top: 360,
    	left: 0
    });
    win.add(svg2);

    var img = Ti.UI.createImageView({
    	width: 100,
    	height: 100,
    	top: 360,
    	right: 0
    });
    var blob = svgView.toBlob("/test.svg");
    img.image = blob;
    win.add(img);
}

win.add(svg1);
win.open();
```

You can change your file dynamically with the setImage(path) function.

```javascript
var image = 'android.svg';
svg.setImage(image);
```


Or simply use it to set an image to a button :

```javascript
var svg = svgView.createView({
	image: "android.svg",
	width: '50',
	height: '50',
	top: 0,
	left: 0,
	backgroundColor:'pink'
});

var svgImage = svg.toImage().media;
$.buttonSvg.setImage(svgImage);
```

## Properties:

* image (String): URL of a file. Android supports inline SVGs too (has to start with `<`)

## Methods:

* toBlob (String, returns TiBlob): URL of a file/SVG string. Converts SVG to a blob (Android only).


## Building module

Go into `android/` or `ios/` and run:

```
ti build -p android --build-only
ti build -p ios --build-only
```


## License
The MIT License (MIT)

Copyright © 2015 Géraud Bourdin

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
