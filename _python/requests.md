---
title:  "Requests"
layout: default

---

# Requests

- Q: How to make a `get` request? What about `post`, `put`, `delete`, `head`, `options`?

- Q: How to suppress ignore SSL exceptions? To suppress `InsecureRequestWarning`? --- A:
`requests.get(..., verify=False)`. You can also do `urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)`.
A context manager to monkey patch existing things: <https://stackoverflow.com/questions/15445981/how-do-i-disable-the-security-certificate-check-in-python-requests/15445989#15445989>


<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=python -- flask">
    <p>Your browser does not support iframes.</p>
</iframe>



```
r = requests.post('https://httpbin.org/post', data = {'key':'value'})
r = requests.put('https://httpbin.org/put', data = {'key':'value'})
r = requests.delete('https://httpbin.org/delete')
r = requests.head('https://httpbin.org/get')
r = requests.options('https://httpbin.org/get')

payload = {'key1': 'value1', 'key2': 'value2'}
r = requests.get('https://httpbin.org/get', params=payload)
print(r.url)   # keys with None value are not added to query

payload = {'key1': 'value1', 'key2': ['value2', 'value3']}   # => https://httpbin.org/get?key1=value1&key2=value2&key2=value3

r = requests.get('https://api.github.com/events')
r.text
r.encoding
r.content   # b'...', gzip and deflate are done for you
r.status_code

from PIL import Image
from io import BytesIO
i = Image.open(BytesIO(r.content))

r.json()   # raises ValueError if it's not a json response


if r: <=> if r.ok:
if r.status_code == 404:
    ...
try:
    r.raise_for_status()   # raises for 4xx and 5xx
except requests.exceptions.HTTPError as e:
    status_code = e.response.status_code
    
if response.status_code // 100 * 100 == 200:
    ...
```
