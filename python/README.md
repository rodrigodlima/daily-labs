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

## Timing code

```python
import time
t0 = time.perf_counter()
...
print(f'{time.perf_counter()-t0:.3f}s')
```

## List comprehension with condition

```python
evens = [x for x in range(20) if x % 2 == 0]
```

## Read env var with default

```python
import os
port = int(os.getenv('PORT', '8080'))
```
