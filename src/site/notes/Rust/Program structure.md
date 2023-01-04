---
{"dg-publish":true,"permalink":"/rust/program-structure/"}
---

# Program Structure

An overview of a Rust program’s structure.

### Installing Rust

We can install Rust by following the directions for your operating system at [rustup.rs](https://rustup.rs/).

Once complete, we will have the following terminal applications installed on our system:

-   `rustc` is the rust compiler.
-   `rustup` manages our Rust version.
-   `cargo` is our main tool used during development.

[These three programs](https://www.codecademy.com/courses/rust-for-programmers/articles/tooling-rust) are all we need to begin writing great software in Rust.

### Creating a New Crate

With Cargo, a project is called a _package_ and packages can consist of one or multiple _crates_. If a package only has a single crate, it is often just called a “crate.”

We can create a new binary crate with the `cargo new` command followed by the desired name of our crate.

```shell
# New binary executable with the name "my_binary".
cargo new my_binary
```

This will create a folder named `my_binary` with the following directory structure:

```
├── src/
│  └── main.rs
└── Cargo.toml
```

All our Rust source code will be contained within the `src` directory. **Cargo.toml** serves as the configuration file for our crate.

If we are creating a library instead of an executable, we can utilize the `--lib` flag:

```shell
# New library with the name "my_library"
cargo new --lib my_library
```

This will create a **lib.rs** file in our `src/` directory instead of a **main.rs** file.

```
├── src/
│  └── lib.rs
└── Cargo.toml
```

All crates require either one of these files to build successfully.

### Program Structure

When creating a binary crate, Cargo will provide us with the following code in our **main.rs** file:

```Rust
fn main() {
	println!("Hello, world!");
}
```

All binary programs require a `main()` function which serves as the entry point for our program. If we run this program with `cargo run`, our terminal will print the line “Hello, world!”.

Rust interprets its source code from left to right, top to bottom. All lines of code are operated on in the order in which they are declared.

Library crates have no point of entry, but it is important to remember that we need to [manually](https://www.codecademy.com/courses/rust-for-programmers/articles/scope-and-ownership) export items we want users of our library to be able to access.

### Naming Conventions

To help us read Rust source code, the language separates constructs by case naming conventions

The `UpperCamelCase` convention is reserved for types and traits:

```Rust
struct UnitStruct; 

struct TupleStruct(T); // ... with generic type T 

struct StructName {  
	field: NamedTuple,
} 

enum EnumName { 
	VariantName,
} 

type TypeAlias = u8; 

trait TraitName {}
```

Items that follow the `snake_case` convention are reserved for attributes, variables, functions, and macros:

```Rust
// Attributes
#![attribute_name] 

// Variableslet 
variable_name = true; 

// Functionsfn 
function_name() {    
	function_call();
} 

// Macros
macro_name!();
macro_name![];
macro_name! {};
```

`SCREAMING_SNAKE_CASE` names are reserved for constants:

```Rust
const EIGHTY_EIGHT: u32 = 88;
```

---

### Cargo Commands

Here is a list of commonly utilized cargo commands and their purpose.

```shell
cargo new             # Create a new binary executable crate
cargo new --lib       # Create a new library crate 

cargo build           # Compiles our crate
cargo build --release # Compiles our crate with optimizations
cargo run             # Compiles our crate and runs the compiled executable 

cargo test            # Run all tests in a crate
cargo doc --open      # Build and open our crate's documentation in a web browser
cargo clean           # Cleans up temporary files created during compilation
cargo publish         # Publishes your crate to `crates.io` 

cargo install         # Installs a binary directly from crates.io
```