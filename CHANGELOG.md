# Changelog

This changelog is based on [Keep a Changelog 1.0.0](https://keepachangelog.com/en/1.0.0).

This project adheres to [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0).

## [Unreleased]

### Added

- DSL function `SessionOption` (#6)

## [0.2.1] - 2021-11-20

### Fixed

- The default directory and shell apply to manually created windows (#2)

## [0.2.0] - 2021-09-13

### Added

- `-l`|`--list` option
- DSL function `EnvVar`
- DSL function alias `Cmd`
- DSL function alias `Dir`
- DSL function alias `Env`
- DSL function alias `Source`

### Fixed

- DSL function `Split` now passes options and sets pane ID

## [0.1.0] - 2021-07-22

### Added

- `mx` script
- `--tmux` option
- `--log` option
- `--version` option
- `-h`|`--help` option
- DSL function `Command`
- DSL function `Directory`
- DSL function `Layout`
- DSL function `Session`
- DSL function `Shell`
- DSL function `SourceFile`
- DSL function `Split`
- DSL function `Window`
