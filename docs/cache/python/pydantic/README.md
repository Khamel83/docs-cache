# Pydantic Documentation

> Source: https://docs.pydantic.dev/
> Cached: 2026-02-13

## Overview

Data validation and settings management using Python type annotations.

_pydantic_ enforces type hints at runtime, and provides user friendly errors when data is invalid.

Define how data should be in pure, canonical Python; validate it with _pydantic_.

## Example

```python
from datetime import datetime
from pydantic import BaseModel

class User(BaseModel):
    id: int
    name = 'John Doe'
    signup_ts: datetime | None = None
    friends: list[int] = []

external_data = {
    'id': '123',
    'signup_ts': '2019-06-01 12:22',
    'friends': [1, 2, '3'],
}
user = User(**external_data)
print(user.id)
#> 123
print(repr(user.signup_ts))
#> datetime.datetime(2019, 6, 1, 12, 22)
print(user.friends)
#> [1, 2, 3]
```

## What's going on here:

- `id` is of type int; the annotation-only declaration tells _pydantic_ that this field is required. Strings, bytes or floats will be coerced to ints if possible; otherwise an exception will be raised.
- `name` is inferred as a string from the provided default; because it has a default, it is not required.
- `signup_ts` is a datetime field which is not required (and takes the value `None` if it's not supplied). _pydantic_ will process either a unix timestamp int (e.g. `1496498400`) or a string representing the date & time.
- `friends` uses Python's typing system, and requires a list of integers. As with `id`, integer-like objects will be converted to integers.

## Validation Errors

If validation fails pydantic will raise an error with a breakdown of what was wrong:

```python
from pydantic import ValidationError

try:
    User(signup_ts='broken', friends=[1, 2, 'not number'])
except ValidationError as e:
    print(e.json())
```

## Rationale

**plays nicely with your IDE/linter/brain**
: There's no new schema definition micro-language to learn. If you know how to use Python type hints, you know how to use _pydantic_.

**dual use**
: _pydantic's_ BaseSettings class allows _pydantic_ to be used in both a "validate this request data" context and in a "load my system settings" context.

**fast**
: _pydantic_ has always taken performance seriously, most of the library is compiled with cython giving a ~50% speedup.

**validate complex structures**
: use of recursive _pydantic_ models, `typing`'s standard types (e.g. `List`, `Tuple`, `Dict` etc.) and validators allow complex data schemas to be clearly and easily defined.

**extensible**
: _pydantic_ allows custom data types to be defined or you can extend validation with methods on a model decorated with the `validator` decorator.

**dataclasses integration**
: As well as `BaseModel`, _pydantic_ provides a `dataclass` decorator which creates (almost) vanilla Python dataclasses with input data parsing and validation.

## Notable Users

- **FastAPI** - a high performance API framework based on _pydantic_
- **Microsoft** - numerous Windows and Office services
- **Amazon Web Services** - gluon-ts time series library
- **Uber** - Ludwig TensorFlow wrapper
