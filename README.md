# Flask-Staticify

This is a simple extension that helps you to serve static files if they doesn't exist from the ad hoc folder. 

Created to work nicely with [Grunt](http://gruntjs.com/) or any [other](http://www.gnu.org/software/make/) build tools that handle your fancy static files.

## Usage
Let's have an example of compiling CoffeeScript to JavaScript (with [grunt-contrib-coffee](https://github.com/gruntjs/grunt-contrib-coffee) and [grunt-usemin](https://github.com/yeoman/grunt-usemin)), using `.tmp` for output dir and the following block:

```html
Please note this file doesn't exist.

<!-- build:js static/optimized.js -->
<script src="/static/app.js">
<!-- endbuild -->
```

After running compile command: `static/app.coffee -> .tmp/app.js`. To use compiled file while development mount the`.tmp` folder to the Flask application : 

~~~python
>>> from flask.ext.staticify import mount_folder
>>> if flask_app.debug:
...     # Mount will monkey the "static" endpoint function 
...     # to look also into the .tmp folder as a fallback.
...     mount_folder(flask_app, '.tmp')

>>> flask_app.test_client().get('/static/app.js')
... <Response [200 OK]>
~~~

And that's it! 

## Install
    $ pip install flask-staticify
