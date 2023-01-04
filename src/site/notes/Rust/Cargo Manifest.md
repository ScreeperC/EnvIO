---
{"dg-publish":true,"permalink":"/rust/cargo-manifest/"}
---

# Cargo Manifest

Learn about cargo manifest files in Rust.

Cargo has a configuration file, also known as a _manifest file_, which helps us manage dependencies, compilation options, and package metadata, and is crucial when uploading your project to [`crates.io`](https://www.codecademy.com/courses/rust-for-programmers/articles/crates-io-rust).

### Cargo.toml

When creating a project with `cargo new`, a default **Cargo.toml** manifest file will be created with the following structure:

```
[package]name = "mybinary"
version = "0.1.0"
edition = "2021" 

[dependencies]
# We can specify external dependencies here
```

If you are unfamiliar with the **toml** file format, you can learn about its syntax [here](https://toml.io/).

### Metadata

The `[package]` table of our manifest file contains metadata about our crate. Here is an overview of some of the most commonly encountered fields:

```shell
[package]name = "mybinary"  # The crate name
version = "0.1.0"  # The crate's current version
edition = "2021"   # Which "Rust Edition" the crate utilizes 

description = ""   # A description of our crate for `crates.io`
keywords = ""      # Keywords for searches on `crates.io`
documentation = "" # URL to the crate's documentation
homepage = ""      # URL to the crate's homepage
repository = ""    # URL of the crate's source repository
authors = [""]     # The authors of the crate
license = ""       # The crate's license
rust-version = ""  # The minimum supported Rust version
```

#### Rust Editions

The `edition` field denotes which _Rust Edition_ the crate utilizes. Rust Editions are not the same as `rustc` compiler versions. Editions are released every few years and are intended mainly for backwards incompatible changes to the language.

We will use the `2021` edition for all examples in this course. To view the specific changes between Rust Editions we can run the command `rustup doc --edition-guide`.

### Dependencies

We can utilize external libraries by declaring them as dependencies. To declare a dependecy, we add the crate name and the desired version number under the `[dependencies]` table.

```shell
[dependencies]serde = "1.0.2"      # Uses version "1.0.2"
serde_derive = "1.0" # Uses version "1.0.X"
heck = "*"           # Uses version "X.X.X"
```

Versioning has a multitude of ways to deal with complex dependency resolution. More information about Cargo’s semantic versioning can be found in the [The Cargo Book](https://doc.rust-lang.org/cargo/reference/resolver.html)

When adding dependencies in this manner, Cargo will automatically download the source code for these libraries from [crates.io](https://crates.io/) and utilize them when compiling our crate.

We can also pull dependencies directly from a git repository with the `git` field:

```shell
serde = { git = "https://github.com/serde-rs/serde" } 

# A specific branch
serde = { git = "https://github.com/serde-rs/serde", branch = "next" } 

# A specific commit hash
serde = { git = "https://github.com/serde-rs/serde", rev = "7e19ae8c9486a3bbbe51f1befb05edee94c454f9" }
```

Pulling dependencies from our local filesystem is possible with the `path` field:

```shell
my_library = { path = "./../my_library" }
```

#### Features

Some crates have parts of their library behind a feature gate. We can enable specific features with the `features` field.

```shell
# The `features` field always takes an array of values
uuid = { version = "0.8", features = ["serde", "v4"] } 

# We can disable features that are added by default.
wee_alloc = { version = "0.4.5", default_features = false }
```

### Additional Configuration

We are capable of many other things within our manifest file such as specifying [`[dev-dependencies]`](https://doc.rust-lang.org/cargo/reference/specifying-dependencies.html#development-dependencies), declaring [`[features]`](https://doc.rust-lang.org/cargo/reference/features.html) for our own crate, creating a [`[profile]`](https://doc.rust-lang.org/cargo/reference/profiles.html) for specific compilation settings, and even making a [`[workspace]`](https://doc.rust-lang.org/cargo/reference/workspaces.html) for managing multiple crates within the same package.

For a comprehensive list of all available functionality, check out Cargo’s reference guide for the [Manifest Format](https://doc.rust-lang.org/cargo/reference/manifest.html).