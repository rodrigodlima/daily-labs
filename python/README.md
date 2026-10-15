# Python notes

Short, practical notes collected while studying and testing.

## Simple HTTP server

```python
python3 -m http.server 8080
```

## Pretty-print JSON from stdin

```python
cat file.json | python3 -m json.tool
```

## Virtualenv in one line

```python
python3 -m venv .venv && . .venv/bin/activate
```

## Dataclasses

```python
from dataclasses import dataclass

@dataclass
class User:
    name: str
    age: int = 0
```

## Pathlib basics

```python
from pathlib import Path
for p in Path('.').rglob('*.py'):
    print(p)
```

## Context manager with contextlib

```python
from contextlib import contextmanager

@contextmanager
def opened(p):
    f = open(p)
    try:
        yield f
    finally:
        f.close()
```

## Argparse skeleton

```python
import argparse
p = argparse.ArgumentParser()
p.add_argument('--verbose', action='store_true')
args = p.parse_args()
```
