# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

[upgrade-percona-key]: upgrade-percona-key.yml
[infra-data]: infra-data.yml

## [Unreleased]

## [0.2.0] - 2017-03-08
### Added
- This CHANGELOG
- [upgrade-percona-key][] to avoid upgrade hang.

### Changed
- Uses `data_version v0.15.2` for [infra-data][] which adds a new
  group defining `http_proxy` and `https_proxy` for all nodes who need
  a proxy.
