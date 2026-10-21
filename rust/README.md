# Rust notes

Short, practical notes collected while studying and testing.

## Check without building

```rust
cargo check
```

## Run clippy as errors

```rust
cargo clippy -- -D warnings
```

## Option combinators

```rust
let len = name.as_deref().map(str::len).unwrap_or(0);
```

## Result with ? operator

```rust
fn read() -> std::io::Result<String> {
    std::fs::read_to_string("cfg.toml")
}
```

## Derive common traits

```rust
#[derive(Debug, Clone, PartialEq)]
struct Config { port: u16 }
```

## Iterators instead of loops

```rust
let total: i32 = v.iter().filter(|x| **x > 0).sum();
```

## Cargo workspace

```toml
[workspace]
members = ["core", "cli"]
```

## Simple error with thiserror

```rust
#[derive(thiserror::Error, Debug)]
enum AppError {
    #[error("not found: {0}")]
    NotFound(String),
}
```
