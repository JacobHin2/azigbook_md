# Introduction

## Installing and setting up Zig

For the time being, the book supports the `master` release of Zig.

This is to take advantage of any new features, bugfixes etc introduced between versions.

Download the `master` zig compiler from [ziglang.org](https://ziglang.org/download/), selecting your OS and architecture e.g. `zig-windows-x86_64` if you use Windows 64bit.

If you cannot see a binary release for your system, try seeing if you can [build from source](), but don't expect everything to work if you use some unsupported system.

Extract the files from the archive.

It helps to place this in a folder that won't get deleted e.g. `$HOME/zig` on Linux/Mac.

Now you need to setup your PATH variable.

### Windows

-----

__A Note For Windows Users:__

Currently, the Zig compiler requires you to use spaces instead of tabs
and Unix line return (LF). On most editors, you can configure this in
the status bar (near the lower right-hand corner). If you use Notepad,
you can get a new editor like Notepad++ or Visual Studio Code, those are
free.


System wide (admin Powershell):
```powershell
[Environment]::SetEnvironmentVariable(
   "Path",
   [Environment]::GetEnvironmentVariable("Path", "Machine") + "C:\your-path\zig-windows-x86_64-your-version",
   "Machine"
)
```
User level (Powershell):
```powershell
[Environment]::SetEnvironmentVariable(
   "Path",
   [Environment]::GetEnvironmentVariable("Path", "User") + ";C:\your-path\zig-windows-x86_64-your-version",
   "User"
)
```

### Linux, macOS and BSD

You can add an export line to your shell startup script (.profile, .zshrc, …)
by adding the Zig install directory to the `PATH` variable.
```sh
export PATH=$PATH:~/path/to/zig-folder
```