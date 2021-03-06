### Fork Note:  This uses some minor modifications of my own combined with the work of Tommy-Carlos Williams and ThalesValentim to return the absolute path of the image in IOS, with a semi-unique filename.  Usage remains the same.  Essentially, it has been brought inline with the android version. It now supports latest cordova version on both android and ios.

Canvas2ImagePlugin
============

This plugin allows you to save the contents of an HTML canvas tag to the iOS Photo Library, Android Gallery or WindowsPhone 8 Photo Album from your app.
On Android platforms you can change the format of the saved files (png/jpg) and define the folder where to save the pictures .

See an example project using it here: [https://github.com/devgeeks/Canvas2ImageDemo](https://github.com/devgeeks/Canvas2ImageDemo) - note: this app does not work in wp8.


Installation
------------

### For Cordova 3.0.x:

1. To add this plugin just type: `cordova plugin add https://github.com/wbt11a/Canvas2ImagePlugin.git` or `phonegap local plugin add https://github.com/wbt11a/Canvas2ImagePlugin.git`
2. To remove this plugin type: `cordova plugin remove org.wbt11a.Canvas2ImagePlugin` or `phonegap local plugin remove org.wbt11a.Canvas2ImagePlugin`

### NOTE: For older versions of Cordova (You will probably have to use tag 0.2.0)


Usage:
------

Call the `window.canvas2ImagePlugin.saveImageDataToLibrary()` method using success and error callbacks and the id attribute or the element object of the canvas to save:

### Example
```html
<canvas id="myCanvas" width="165px" height="145px"></canvas>
```

```javascript  ... default format: png   ... default quality 100%
function onDeviceReady()
{
	window.canvas2ImagePlugin.saveImageDataToLibrary(
        function(msg){
            console.log(msg);  //msg is the filename path (for android and iOS)
        },
        function(err){
            console.log(err);
        },
        document.getElementById('myCanvas')
    );
}
```

```javascript  ... format: jpg   ... quality 80%
function onDeviceReady()
{
	window.canvas2ImagePlugin.saveImageDataToLibrary(
        function(msg){
            console.log(msg);  //msg is the filename path (for android and iOS)
        },
        function(err){
            console.log(err);
        },
        document.getElementById('myCanvas'),
        '.jpg',
        80
    );
}

```javascript  ... format: jpg   ... quality 80% ... outputfolder : 'canvaspluginfolder'
function onDeviceReady()
{
	window.canvas2ImagePlugin.saveImageDataToLibrary(
        function(msg){
            console.log(msg);  //msg is the filename path (for android and iOS)
        },
        function(err){
            console.log(err);
        },
        document.getElementById('myCanvas'),
        '.jpg',
        80,
        'cunvaspluginfolder'
    );
}

with this plugin its easy to create a picture, add some text to the picture and save the edited picture to galery or wehre ever you want ! 





## License

The MIT License

Copyright (c) 2011 Tommy-Carlos Williams (http://github.com/devgeeks)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
