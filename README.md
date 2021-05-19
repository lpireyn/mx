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

## Changelog

See [CHANGELOG](CHANGELOG.md).

## Contributing

See [CONTRIBUTING](CONTRIBUTING.md).

## License

mx is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) ([local copy](LICENSE)).
