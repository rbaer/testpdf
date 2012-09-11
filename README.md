### Extension

A Firefox extension is availble in two places:

+ Stable Version: https://addons.mozilla.org/en-US/firefox/addon/pdfjs
+ Development Version: http://mozilla.github.com/pdf.js/extensions/firefox/pdf.js.xpi

The development extension should be quite stable but still might break from time to time.
Also, note that the development extension is updated on every merge and by default Firefox will
auto-update extensions on a daily basis (you can change this through the 
`extensions.update.interval` option in `about:config`).

For an experimental Chrome extension, get the code as explained below and issue `node make extension`. 
Then open Chrome, go to `Tools > Extension` and load the (unpackaged) extension
from the directory `build/chrome`.

### Getting the code

To get a local copy of the current code, clone it using git:

    $ git clone git://github.com/rbaer/testpdf.git pdfjs
    $ cd pdfjs

Next, you need to start a local web server as some browsers don't allow opening
PDF files for a file:// url:

    $ node make server

You can install Node via [nvm](https://github.com/creationix/nvm) or the 
[official package](http://nodejs.org). If everything worked out, you can now serve 

+ http://localhost:8081/index.html

You can also view all the test pdf files on the right side serving

+ http://localhost:8888/test/pdfs/?frame

### Building pdf.js.

In order to bundle all `src/` files into a final `pdf.js` and build the generic viewer, issue:

    $ node make generic

This will generate the file `build/generic/build/pdf.js` that can be included in your final project. The pdf.js file is large and should be minified for production. Also, if you would like to support more browsers than firefox you'll also need to include `compatibility.js` from `build/generic/web/`.


  

