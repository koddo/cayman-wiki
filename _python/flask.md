---
title:  "Flask"
layout: default

---

# Misc

<https://github.com/mgood/flask-debugtoolbar>

# Running flask

Use `$ flask run` instead of `Flask.run()` in code, because of code reload: <https://softwareengineering.stackexchange.com/questions/326517/why-is-flask-cli-recommended-over-flask-run>

<http://flask.pocoo.org/docs/1.0/deploying/wsgi-standalone/>

# Routing, variables, and converters.

The `any` converter: <https://github.com/pallets/werkzeug/blob/778f482d1ac0c9e8e98f774d2595e9074e6984d7/werkzeug/routing.py#L1271>

# Questions


- Q: How to handle different HTTP methods using flask? --- A: 

```
@app.route('/login', methods=['GET', 'POST'])
def login():
    if flask.request.method == 'POST':
        ...
```


- Q: How to set a secret key for signed cookies in flask? --- A:
<http://flask.pocoo.org/docs/1.0/quickstart/#sessions>
<https://stackoverflow.com/questions/22463939/demystify-flask-app-secret-key/48596852#48596852>


- Q: How to use `url_for` in flask? --- A: <http://flask.pocoo.org/docs/1.0/api/#flask.url_for>



<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=python -- flask">
    <p>Your browser does not support iframes.</p>
</iframe>



