With `electron-pdf` module we can convert files by command line from any language.
```shell
$ npm install -g electron-pdf
$ sudo apt-get install xvfb # X11 server working in-memory
$ export DISPLAY=':99.0'
$ Xvfb :99 -screen 0 1024x768x24 > /dev/null 2>&1 &
$ electron-pdf source.html output.html
```

Though spawning heavy process for each PDF isn't good idea.
On my i5-6600 spawning process takes 350ms 
and similar single-core performance  on server would significantly damage your company budget.

`electron-pdf` expose programmatic API for this case, but only for Node. 

Though, writing microservice for this task is easy-peasy - 
it took less than 100 lines of code for me (but still too big to place it here).