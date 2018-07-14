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

Example failing tests output:

```console
$ cargo test
   Compiling serde-optional-timespec v0.1.0 (file:///home/daboross/serde-optional-timespec)
    Finished dev [unoptimized + debuginfo] target(s) in 0.86s
     Running target/debug/deps/serde_optional_timespec-dffc3853d9a57b5e

running 8 tests
test tests::parse_number_double_optional_timepsec ... ok
test tests::parse_null_double_optional_timepsec ... FAILED
test tests::parse_number_optional_timepsec ... ok
test tests::parse_null_optional_timepsec ... FAILED
test tests::parse_number_timespec ... ok
test tests::parse_string_optional_timepsec ... FAILED
test tests::parse_string_double_optional_timepsec ... FAILED
test tests::parse_string_timespec ... FAILED

failures:

---- tests::parse_null_double_optional_timepsec stdout ----
	thread 'tests::parse_null_double_optional_timepsec' panicked at 'called `Result::unwrap()` on an `Err` value: Error("invalid type: null, expected an integer or string containing an integer", line: 0, column: 0)', libcore/result.rs:945:5
note: Run with `RUST_BACKTRACE=1` for a backtrace.

---- tests::parse_null_optional_timepsec stdout ----
	thread 'tests::parse_null_optional_timepsec' panicked at 'called `Result::unwrap()` on an `Err` value: Error("invalid type: null, expected an integer or string containing an integer", line: 0, column: 0)', libcore/result.rs:945:5

---- tests::parse_string_optional_timepsec stdout ----
	thread 'tests::parse_string_optional_timepsec' panicked at 'called `Result::unwrap()` on an `Err` value: Error("invalid type: string \"1474674699273\", expected an integer or string containing an integer", line: 0, column: 0)', libcore/result.rs:945:5

---- tests::parse_string_double_optional_timepsec stdout ----
	thread 'tests::parse_string_double_optional_timepsec' panicked at 'called `Result::unwrap()` on an `Err` value: Error("invalid type: string \"1474674699273\", expected an integer or string containing an integer", line: 0, column: 0)', libcore/result.rs:945:5

---- tests::parse_string_timespec stdout ----
	thread 'tests::parse_string_timespec' panicked at 'called `Result::unwrap()` on an `Err` value: Error("invalid type: string \"1474674699273\", expected an integer or string containing an integer", line: 0, column: 0)', libcore/result.rs:945:5


failures:
    tests::parse_null_double_optional_timepsec
    tests::parse_null_optional_timepsec
    tests::parse_string_double_optional_timepsec
    tests::parse_string_optional_timepsec
    tests::parse_string_timespec

test result: FAILED. 3 passed; 5 failed; 0 ignored; 0 measured; 0 filtered out

error: test failed, to rerun pass '--lib'
```
