PhantomJS as headless WebKit isn't designed to generate PDFs. But we can do it!

We need to install it: 
```
$ wget https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-2.1.1-linux-x86_64.tar.bz2
$ tar xvjf phantomjs-2.1.1-linux-x86_64.tar.bz2
$ sudo cp ./phantomjs-2.1.1-linux-x86_64/bin/phantomjs /usr/local/bin
$ phantomjs script.js
```

And script.js must look like:

```javascript
var page = require('webpage').create();
page.open('file://path/to/our/file', function() {
    page.render('output.html');
    phantom.exit();
});
```

As we see, it requires creation of new process every time we need PDF. 
Even if we parametrize this script 
(as it was already done in [official example rasterize.js](https://github.com/ariya/phantomjs/blob/master/examples/rasterize.js)
it's less than ideal.

We have three solutions for this:
* learn to live with it
* write Node.js microservice using `phantom` module and pooling processes
* write your own implementation of PhantomJS controller (Phantom allow to expose simple HTTP based API)