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
