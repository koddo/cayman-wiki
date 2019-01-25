---
title:  "Virtual environments"
layout: default

---

# pip and venv

First install a python version you'd like your venv to be. E.g., using macports. Then:

```
$ python3.7 -m venv ~/.python_venv/test
$ source ~/.python_venv/test/bin/activate
$ pip install --upgrade pip
$ pip install pandas
```

- Q: How to create, activate, and remove a virtual environment?

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=python -- virtual environments">
    <p>Your browser does not support iframes.</p>
</iframe>
