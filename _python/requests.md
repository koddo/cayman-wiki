---
title:  "Requests"
layout: default

---

# Requests

- Q: How to make a `get` request? What about `post`, `put`, `delete`, `head`, `options`?

- Q: How to suppress ignore SSL exceptions? To suppress `InsecureRequestWarning`? --- A:
`requests.get(..., verify=False)`. You can do `urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)`, but make sure you know what you are doing, because it could be a security hole.
A context manager to monkey patch existing things: <https://stackoverflow.com/questions/15445981/how-do-i-disable-the-security-certificate-check-in-python-requests/15445989#15445989>


<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=python -- flask">
    <p>Your browser does not support iframes.</p>
</iframe>
