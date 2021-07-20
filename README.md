# mx

**mx** is a [tmux](https://github.com/tmux/tmux) session manager written as a single [Bash](https://www.gnu.org/software/bash) script.

[![Apache License 2.0](https://img.shields.io/static/v1?label=License&message=Apache%20License%202.0&style=flat-square&color=informational&logo=apache)](https://www.apache.org/licenses/LICENSE-2.0)
[![Semantic Versioning 2.0.0](https://img.shields.io/static/v1?label=Semantic%20Versioning&message=2.0.0&style=flat-square&color=informational)](https://semver.org/spec/v2.0.0)
[![Keep a Changelog 1.0.0](https://img.shields.io/static/v1?label=Keep%20a%20Changelog&message=1.0.0&style=flat-square&color=informational)](https://keepachangelog.com/en/1.0.0)
[![Hosted on GitLab](https://img.shields.io/static/v1?label=Hosted%20on&message=GitLab&style=flat-square&color=informational&logo=gitlab)](https://gitlab.com/lpireyn/mx)

## Quickstart

Create an *mx session* file named `demo.mx`:

``` shell
Session Demo

Window First window
Command echo Hello!

Window Second window

Window Monitoring
Shell top
```

Run it with `mx`:

``` shell
mx demo
```

You should end up in a tmux session with three windows, as specified in `demo.mx`.

## Installation

### Requirements

- [Bash](https://www.gnu.org/software/bash/)
- [tmux](https://github.com/tmux/tmux)

### Installation from sources

Clone the *mx* git repository:

``` shell
git clone https://gitlab.com/lpireyn/mx.git ~/mx
```

This creates a `mx` directory in your home directory, which contains the `mx` script.

For convenience, the `mx` script can be copied to a directory in your `PATH` (typically `~/.local/bin`, `~/bin` or `/usr/local/bin`).

## Usage

| Command line | Description |
| --- | --- |
| `mx` [`--tmux` CMD] [`--log` LOGFILE] [MXFILE] | Executes the mx session file MXFILE |
| `mx --version` | Displays the mx version |
| `mx -h\|--help` | Displays the help |

The mx session file is the first of the following files that is found:

1. If MXFILE is omitted, the file `.mx` in the current directory
2. MXFILE (or MXFILE.mx) in the current directory
3. MXFILE (or MXFILE.mx) in the `$XDG_CONFIG_HOME/mx` directory (`$XDG_CONFIG_HOME` defaults to `~/.config`)

This supports the following common usecases:

- Per-project mx sessions, stored in a `.mx` file in the project root directory
- Per-user mx sessions, stored in `~/.config/mx/*.mx` files (can be managed like other dotfiles)

## DSL functions

An *mx session* file is a Bash script that calls the following *mx DSL functions* to configure the tmux session.

| Function | Description |
| --- | --- |
| `Command` COMMAND [ARGS...] | Executes COMMAND in the current pane (by sending the corresponding keys) |
| `Directory` DIRECTORY | Sets the current directory of the current pane (or the default directory of the session) to DIRECTORY |
| `Layout` LAYOUT | Sets the layout of the current window to LAYOUT |
| `Session` NAME | Starts the session named NAME |
| `Shell` SHELL | Sets the shell command of the current pane (or the default shell command of the session) to SHELL |
| `SourceFile` FILE | Sources the tmux file FILE |
| `Split` | Splits the current window to create a pane |
| `Window` NAME | Starts a window named NAME |

**Note:**
Although it's a Bash script, an mx session file does not need a shebang and does not have to be executable.
However, it can use Bash constructs such as variables, conditions, loops, etc.

## Changelog

See [CHANGELOG](CHANGELOG.md).

## Contributing

See [CONTRIBUTING](CONTRIBUTING.md).

## License

mx is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) ([local copy](LICENSE)).
