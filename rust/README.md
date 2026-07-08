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
