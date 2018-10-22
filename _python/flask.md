---
title:  "Flask"
layout: default

---

# Misc

<https://github.com/mgood/flask-debugtoolbar>

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


# Application and request contexts

<https://stackoverflow.com/questions/20938619/whats-the-difference-between-application-and-request-contexts>
<https://stackoverflow.com/questions/15083967/when-should-flask-g-be-used>

Application context is a lighter version of full-blown request context. It has 


<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=python -- flask">
    <p>Your browser does not support iframes.</p>
</iframe>

