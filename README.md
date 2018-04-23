# Building-Web-APIs-with-Flask ![Learning](https://img.shields.io/badge/learning-in%20progress-orange.svg?style=flat-square)

This repo contains the app built following the Building Web APIs with Flask course by Gergo Bogdan on Lynda.com.

# Setup

Create a folder for the project (or clone the repo). Create a `venv` folder and initialize Virtualenv in this folder:

```
mkdir venv
virtualenv venv/
```

All the necessary tools will be installed:

`Installing setuptools, pip, wheel...done.`

Let's activate the virtual environment, now:

`source venv/bin/activate`

Now we can install Flask using pip:

`pip install flask`

# Application: The first two files

Let's now create two files: `app.py` and `quotes.py`.

In `app.py` we first import Flask and other modules:

```
from flask import Flask, jsonify
import random
```

We also import the quotes that are stored in `quotes.py`:

`from quotes import funny_quotes`

`quotes` is the name of the file, and `funny_quotes` is the only function in this file. The quotes are stored in a dictionary where the key is the author, and the value is the quote.

We then declare a Flask app and pass the name of the current file as parameter:

`app = Flask(__name__)`

The app itself is simple: We import the quotes, calculate the number of quotes based on the length of the dictionary, and use that length to generate a random quote index in the dictionary and pull the corresponding quote. The output of that dictionary is then [returned _jsonified_.](http://flask.pocoo.org/docs/0.12/api/#flask.json.jsonify)

At the end of the script we only start the Flask application if the Python script is started separately. The app is started in debug mode:

```
if __name__ == "__main__":
    app.run(debug=True)
```

# Custom routing configuration



