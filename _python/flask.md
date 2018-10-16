---
title:  "Flask"
layout: default

---

# Misc

<https://github.com/mgood/flask-debugtoolbar>

# Questions

- Q: How to have a route in flask? With variables? --- a: 
```
@app.route('/hello')
def hello():
    return 'Hello, World'
    
@app.route('/user/<username>')
def show_user_profile(username):
    ...
    
@app.route('/post/<int:post_id>')
def show_post(post_id):
    ...
```

- Q: What are converter types for flask routes? ---
string      the default, accepts any text without a slash
int         positive integers
float       positive floats
path        like string, but also accepts slashes
uuid        uuid


- Q: What's the difference between `/projects` and `/projects/` in flask? --- a: <http://flask.pocoo.org/docs/1.0/quickstart/#unique-urls-redirection-behavior>

- Q: How to handle different HTTP methods using flask? --- a: 

```
@app.route('/login', methods=['GET', 'POST'])
def login():
    if flask.request.method == 'POST':
        ...
```

- Q: How to serve static files using flask? How to generate URLs for them? --- a:
Put them in `static/` folder.
To generate URLs for static files use `url_for('static', filename='style.css')`.

- Q: How to set a secret key for signed cookies in flask? --- a:
<http://flask.pocoo.org/docs/1.0/quickstart/#sessions>
<https://stackoverflow.com/questions/22463939/demystify-flask-app-secret-key/48596852#48596852>

- Q: Where to put templates in flask? How to render them? --- a:
Flask looks for templates in the `templates` folder.

```
return render_template('hello.html', name=name)
```

- Q: How to access HTTP method info of request in flask, form data, URL params?

```
if request.method == 'POST':
    ...
request.form['username']
request.args.get('key', '')
```

# Application and request contexts

<https://stackoverflow.com/questions/20938619/whats-the-difference-between-application-and-request-contexts>
<https://stackoverflow.com/questions/15083967/when-should-flask-g-be-used>

Application context is a lighter version of full-blown request context. It has 


<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=python -- flask">
    <p>Your browser does not support iframes.</p>
</iframe>



