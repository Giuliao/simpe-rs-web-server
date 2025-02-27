## Introduction

I have learned Rust and I am interested in developing a Web Framework. So I decide to find some materials to learn and write a framework from scratch. So the basic knowledge I learned from is official documents.

## Build a Multithreaded Web Server

- [x] [20.1 Building a Single-Threaded Web Server](https://doc.rust-lang.org/book/ch20-01-single-threaded.html)
- [x] [20.2 Turning Our Single-Threaded Server into a Multithreaded Server](https://doc.rust-lang.org/book/ch20-02-multithreaded.html)
- [x] [20.3 Graceful Shutdown and Cleanup](https://doc.rust-lang.org/book/ch20-03-graceful-shutdown-and-cleanup.html)

  In this part, I learned following things,
  - The process of clear threaded workers. Firstly, close the channel. Secondly, join all the threads. Thirdly, in the worker listen the channel close and quit.
  - [_dyn_](https://doc.rust-lang.org/std/keyword.dyn.html) keyword, different from [_impl_](https://doc.rust-lang.org/std/keyword.impl.html), it has two pointers, one is a pointer to the object itself, and the other is a pointer to the vtable, which is a table that contains the method names and their implementations.
  - [vec.drain](https://doc.rust-lang.org/std/vec/struct.Drain.html), which is used to remove a range of elements from a vector and return an iterator over them. It will also take the ownership of the deleted element. So in some cases, if there are many mutable references to the vec, we can use drain to clear all the element in it.
  - [option.take](https://doc.rust-lang.org/std/option/enum.Option.html#method.take), which will remove the content from Option, remaining the Option None. In other words, all of the ownership of the content will be transferred to the caller.
