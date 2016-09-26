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

5. Check with your browser: `http://localhost:9000`

## Known Caveats

* Projects created with Ionide seem to generate `.fsproj` with wrong paths (look at
those with `..\packages\...`).
* [Issues](http://stackoverflow.com/q/39559325/747872) with projects created from 
the *Client-Server Web Application as .NET module* and run with `xsp4` (Mono's web
server for development or testing).

## Contributions

PRs and "issues" are more than welcome!  :-)