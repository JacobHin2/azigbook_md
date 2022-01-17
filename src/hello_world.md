# Hello world!

In this chapter, we will print "Hello, world" to the console, a rite of passage of many programming languages.

To get started, open a text editor and create a file called `main.zig` (you may name it anything you like but this is convention and is used in projects using a `build.zig` file, more about that later.).

Lets start by declaring a *main* function, which we need as the entrypoint for any runnable Zig programs.

```zig
pub fn main() void {

}
```
The syntax is fairly simple, but might be a little confusing if you come from a language like Python. `fn` declares a function, the name of which is `main` and this function returns nothing, `void`.

The `pub` keyword is needed because it lets us access this function outside of our file, something useful in larger projects where we might want to break things down. 

A great example of this done right is the Zig standard library.

The reason `pub` needs to be used even if *we* aren't using the main function elsewhere is that under the hood, the Zig standard library does a little *magic* to run your main function.

To check this works, lets run it.

```sh
~ zig run main.zig 
```
The program compiles but it does nothing yet.

To print "Hello, world", we need to import the standard library using `const std = @import("std");` at the top of our file. Now we can use the `std.io.getStdOut().writer()` function, which will give us a handle on **st**an**d**ard **out**put, or stdout, which is where we would want to write our message.

A `writer` is how you write data to a given destination (like a file, a network
stream or a terminal) in Zig. 

Similarly, a reader allows to read data from a
given source.

Lets do it then.

```zig
const std = @import("std");

pub fn main() void {
    const stdout = std.io.getStdOut().writer();
    writer.print("Hello, world\n", .{});
}
```

