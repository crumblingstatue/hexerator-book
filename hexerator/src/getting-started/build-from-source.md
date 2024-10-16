# Building from source

## Prerequisites

- Up-to-date nightly [Rust](https://www.rust-lang.org/)
- A C++ compiler and [CMake](https://cmake.org/) for building some native dependencies.

## Steps

1. Get the latest source zip or tarball from the [releases page](https://github.com/crumblingstatue/hexerator/releases).
2. Extract the source somewhere
3. Ensure you're using an up-to-date nightly rust. Hexerator is using nightly Rust for the time being.
4. Open up a terminal, and change to the directory where you extracted Hexerator.
5. Run `cargo build --release`
6. There will be a hexerator binary built in the `target/release` directory.

If you run into trouble you can't seem to solve, you can ask for help at <https://github.com/crumblingstatue/hexerator/discussions>.
