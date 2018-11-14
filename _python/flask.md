---
title:  "Flask"
layout: default

---

<https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-ix-pagination>

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

# Trailing slash in URLs

From <http://flask.pocoo.org/docs/1.0/quickstart/#unique-urls-redirection-behavior>:

The canonical URL for the projects endpoint has a trailing slash. It’s similar to a folder in a file system. If you access the URL without a trailing slash, Flask redirects you to the canonical URL with the trailing slash.

The canonical URL for the about endpoint does not have a trailing slash. It’s similar to the pathname of a file. Accessing the URL with a trailing slash produces a 404 “Not Found” error. This helps keep URLs unique for these resources, which helps search engines avoid indexing the same page twice.



# Application and request contexts

<https://stackoverflow.com/questions/20938619/whats-the-difference-between-application-and-request-contexts>
<https://stackoverflow.com/questions/15083967/when-should-flask-g-be-used>

Application context is a lighter version of full-blown request context.


<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=python -- flask">
    <p>Your browser does not support iframes.</p>
</iframe>

# flask-wtf

- Q: How to define a form using flask-wtf?
- A:

```
class MyForm(FlaskForm):
    name = StringField('name', validators=[DataRequired()])
    submit = SubmitField('say hello')
```

```
<form action="" method="post" novalidate>
    {{ form.hidden_tag() }}
    <p>
        {{ form.name.label }}<br>
        {{ form.name(size=32) }}
    </p>
    <p>{{ form.submit() }}</p>
</form>
```

```
@app.route('/submit', methods=('GET', 'POST'))
def submit():
    form = MyForm()
    if form.validate_on_submit():
        return redirect('/success')
    else:
        return render_template('wtf.jinja', form=form)
```


- Q: What fields can you have in flask-wtf?
- A:

- Q: How to have a custom validation function for flask-wtf form?
- A: <http://flask.pocoo.org/snippets/64/>

- Q: `Form()` formdata vs data vs obj?
- A: <https://stackoverflow.com/questions/42984453/wtforms-populate-form-with-data-if-data-exists>

