---
{"dg-publish":true,"permalink":"/rust/why-rust/"}
---

# Why Rust?

Let’s look through a few things to keep in mind about Rust before we decide to use it.

If you are looking to create performant and memory-safe software while using a multitude of programming paradigms, Rust just might be the language for you.

### Safety

The biggest advantage of Rust over most other languages is the inherent memory safety of the language. When software is _memory safe_, it will not accidentally leak memory or encounter many of the bugs related to the programming concept of _null_.

Once you start using the language, you will realize that you can create powerful error-free software. It’s good to know your code will not crash unless you tell it to!

The tradeoff to this is that we must manage memory manually in our codebase. This introduces concepts such as [`Lifetimes`](https://www.codecademy.com/courses/rust-for-programmers/articles/lifetimes-rust), which we generally do not encounter in other languages. In the long run, it would seem the extra complexity is worth the rewards.

### Performance

Rust is very performant; in fact, it is on par with the speed of other low-level languages such as `C` and `C++`.

That said, It is also important to remember that in some situations, computational performance may be inconsequential. For example, a few milliseconds of saved computation might not be worth the extra work of porting an entire Ruby program into Rust.

### Domain

Rust is a general-purpose language and has the ability to fall into any domain. The only thing stopping Rust from being proficient in any specific domain is time.

Are you making a video game? There are many stable scripting languages and frameworks which are designed specifically for game development.

Do you need to utilize a GUI library? There are also many GUI frameworks available at varying stages of maturity.

Do you need to write asynchronous software? Rust is advancing in this field every day.

Does your code have to interact with another language? Rust already has many mature libraries to interconnect with other languages.

Does your code have to run on a unique architecture? Rust currently has 178 different built-in architecture compilation targets.

### Is it for you?

The most important question. Rust may have more complexity, but the knowledge learned is invaluable on the path to understanding the art of programming as a whole. Once you have mastered these new concepts and are comfortable writing in Rust, you will feel as though you have a better understanding of what your code is actually doing.

Another very important factor is whether or not you enjoy writing in it. Some people prefer the syntax and functional approach of “Lisp”-like languages, while some find the structure of object-oriented languages such as “Smalltalk” to be invaluable.

And some use Rust because they find it to be a beautiful programming language that just keeps getting better.