# WebSharper Samples

This repository contains simple [WebSharper](http://websharper.com/) projects,
written in F#, prepared to run on Linux with Mono.

## Motivation

Interested to know about the applicability of WebSharper for real projects and coming
from the Linux world (I never used .NET before), I tried to run some experiments but
I got frustrated with the available tools and documentation for just "getting
started" (look at this [question](http://stackoverflow.com/q/39559325/747872)).

In summary, the main motivation for this repository is to help people to get started
with F# and WebSharper.

## Requirements

Supposing you are running on a Debian/Ubuntu environment:

* `mono-devel`
* `mono-runtime`
* `fsharp`

### Editor

To run this project, you don't need to use any specific editor, but 
[VS Code](https://code.visualstudio.com) integrates well with F# (no surprises) and
has some useful plugins (like [Vim keybindings](https://github.com/VSCodeVim/Vim) 
and [Ionide](http://ionide.io/)).

[vim-sharp](https://github.com/fsharp/vim-fsharp) seems full of features too, but I
found it too heavy for a common Vim experience.

## Usage

1. Fetch `paket.exe` by running `mono .paket/paket.bootstrapper.exe`.

2. Download and install the dependencies with `mono .paket/paket.exe install`.

3. Compile the code:

```sh 
cd wsnextui/WsNextui 
xbuild
```

4. Exectute the self-hosted web server:

```sh 
cd bin
mono WsNextui.exe
```

5. Check the following URL with your browser: `http://localhost:9000`

## Known Caveats

* Projects created with Ionide seem to generate `.fsproj` with wrong paths (look at
those with `..\packages\...`).
* There are some [issues](http://stackoverflow.com/q/39559325/747872) about running
*Client-Server Web Application as .NET module* <sup>[1](#clientServerModule)</sup> with 
`xsp4` (Mono's web server for development or testing).
* The file `Web.config` is a little tricky. For **WsNextui**, `Web.config` should be
present in the source code directory for the compilation step in order to have the
compiled JS (F# to JS) files, even if this file is empty (look at 
[this question](http://websharper.com/question/80845/can-t-load-javascript-from-browser)).

<a name="clientServerModule">[1]</a>: These kind of projects don't generate `.exe` files,
but only `.dll` files.

## Contributions

PRs and "issues" are more than welcome!  :-)
