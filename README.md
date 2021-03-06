
# JSON Validation Schema




<a href="https://travis-ci.org/RobusGauli/jsonvalidate">
    <img src="https://travis-ci.org/RobusGauli/jsonvalidate.svg?branch=master">
</a>

<a href="https://pypi.python.org/pypi/jsonvalidate">
    <img src="https://img.shields.io/pypi/v/jsonvalidate.svg">
</a>

<a href="https://jsonvalidate.readthedocs.io/en/latest/?badge=latest">
    <img src="https://readthedocs.org/projects/jsonvalidate/badge/?version=latest">
</a>


JSON Validation Schema


* Free software:  MIT license
* Documentation:  https://jsonvalidate.readthedocs.io.


Features
------------

```python
from jsonvalidate import Object, String, Integer

schema = Object({
    'email': String(regex='[^@]+@[^@]+\.[^@]+'),
    'name': String(),
    'age': Integer(enums=[5, 6, 7]),
    'address': Object({
        'permanent': String(),
        'temporary': String(min_length=3, enums=['asss', 's'])
    })
})

payload = {
    'email': 'robus@example.com',
    'name': 'robus',
    'age': 342,
    'address': {
        'permanent': 'sd',
        'temporary': 'asss'
    }

}

print(schema.check(payload))
```
