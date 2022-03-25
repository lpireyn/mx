# Changelog

This changelog is based on [Keep a Changelog 1.0.0](https://keepachangelog.com/en/1.0.0).

This project adheres to [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0).

## [Unreleased]

### Added

- Make mx files parameterizable (#11)

## [0.4.0] - 2021-11-29

### Added

- `mx` checks the version of Bash and fails if it's earlier than 4.0 (#10)

## [0.3.1] - 2021-11-24

### Fixed

- Removed useless and potentially problematic option `-g` in call to `declare`

## [0.3.0] - 2021-11-21

### Added

- DSL function `SessionOption` (#6)
- DSL function `WindowOption` (#7)
- DSL function `Clock` (#4)

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
