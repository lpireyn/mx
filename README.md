# mx

**mx** is a [tmux](https://github.com/tmux/tmux) session manager written as a single [Bash](https://www.gnu.org/software/bash) script.

[![Pipeline](https://img.shields.io/gitlab/pipeline/lpireyn/mx/master?label=Pipeline&style=flat-square&logo=gitlab)](https://gitlab.com/lpireyn/mx/-/commits/master)
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

```
Usage: mx [OPTION]... [FILE]
Execute the tmux session defined in the mx FILE.

If a tmux session with the same name already exists, the tmux client attaches to it,
otherwise the session is created.

FILE is looked for in the current directory, then in '$XDG_CONFIG_HOME/mx',
with and without the '.mx' extension.
$XDG_CONFIG_HOME defaults to '$HOME/.config'.
FILE defaults to '.mx' in the current directory.

mx does not execute a session if $TMUX is already set.

Options:
  -l|--list    Lists the available mx sessions and exits
  --tmux CMD   Specifies the tmux command to use
               Defaults to $MX_TMUX, then to 'tmux'
  --log FILE   Logs the tmux commands in FILE
  --version    Displays the mx version and exits
  -h|--help    Displays this help and exits
```

mx supports the following common usecases out of the box:

- Per-project mx sessions, stored in a `.mx` file in the project root directory
- Per-user mx sessions, stored in `~/.config/mx/*.mx` files (can be managed like other dotfiles)

## DSL functions

An *mx session* file is a Bash script that calls the following *mx DSL functions* to configure the tmux session.

| Function | Description |
| --- | --- |
| `Cmd` | Alias of `Command` |
| `Command` COMMAND [ARGS...] | Executes COMMAND in the current pane (by sending the corresponding keys) |
| `Dir` | Alias of `Directory` |
| `Directory` DIRECTORY | Sets the current directory of the current pane (or the default directory of the session) to DIRECTORY |
| `Env` | Alias of `EnvVar` |
| `EnvVar` NAME [VALUE] | Sets environment variable NAME to VALUE (or null) in the current pane (or in all panes of the session)
| `Layout` LAYOUT | Sets the layout of the current window to LAYOUT (see [Layouts](#layouts)) |
| `Session` NAME | Starts the session named NAME |
| `Shell` SHELL | Sets the shell command of the current pane (or the default shell command of the session) to SHELL |
| `Source` | Alias of `SourceFile` |
| `SourceFile` FILE | Sources the tmux file FILE |
| `Split` | Splits the current window to create a pane |
| `Window` NAME | Starts a window named NAME |

**Note:**
Although it's a Bash script, an mx session file does not need a shebang and does not have to be executable.
However, it can use Bash constructs such as variables, conditions, loops, etc.

## Layouts

tmux supports the following layouts:

- `even-horizontal`
- `even-vertical`
- `main-horizontal`
- `main-vertical`
- `tiled`
- Custom layouts

See the [`select-layout` tmux command](http://man.openbsd.org/OpenBSD-current/man1/tmux.1#select-layout) for details.

## Changelog

See [CHANGELOG](CHANGELOG.md).

## Contributing

See [CONTRIBUTING](CONTRIBUTING.md).

## License

mx is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) ([local copy](LICENSE)).
