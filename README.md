# Flask-Staticify

This is a pretty simple extension that helps you to serve static files if they doesn't exist from the ad hoc folder. 

## Usage 

Usage is simple:

~~~python
from flask.ext.staticify import mount_folder

if flask_app.debug:
    # Mount will monkey the "static" endpoint function 
    # to look also into the .tmp folder as a fallback.
    mount_folder(flask_app, '.tmp')
~~~

## Install
    $ pip install flask-staticify
