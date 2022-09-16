# Building from source

## Prerequisites

- Up-to-date nightly [Rust](https://www.rust-lang.org/)
- [SFML](https://www.sfml-dev.org/) 2.5
- A C++ compiler for building some native dependencies (GCC, Clang, MSVC)

## Steps

1. Get the latest source zip or tarball from the [releases page](https://github.com/crumblingstatue/hexerator/releases).
2. Extract the source somewhere
3. Make sure you have SFML set up correctly. You might need to [set some environment variables](https://github.com/jeremyletang/rust-sfml#environment-variables).
4. Ensure you're using an up-to-date nightly rust. Hexerator is using nightly Rust for the time being.
5. Open up a terminal, and change to the directory where you extracted Hexerator.
6. Run `cargo build --release`
7. There will be a hexerator binary built in the `target/release` directory.
8. On windows, you might need to copy over the `.dll` files from the `bin` folder of your SFML location.
   Do this if you're getting .dll related errors.
   Try copying the .dll files to wherever you will be running Hexerator from.

If you run into trouble you can't seem to solve, you can ask for help at <https://github.com/crumblingstatue/hexerator/discussions>.
