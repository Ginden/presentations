`wkhtmltopdf` is simple tool built on top of QtWebKit. 
It's easy to use from C and other languages providing bindings for C (like Java)... Or just from command line.

```shell
$ sudo apt install wkhtmltopdf
$ wkhtmltopdf invoice.html output.html
```

`wkhtmltopdf` is solid solution, but it uses rather outdated `QtWebKit`.

Its engine is over 2 years now and doesn't support most recent CSS and HTML features.
Support for capturing SPA is limited too.
