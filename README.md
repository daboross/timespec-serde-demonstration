To run tests successfully:

```
cargo update --package serde_json --precise 1.0.14
cargo test
```

To run tests unsuccessfully:

```
cargo update --package serde_json --precise 1.0.15
cargo test
```
