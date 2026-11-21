# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).


## [Unreleased]

### Changed
- Recommend the `pull_request` trigger instead of `pull_request_target`, which GitHub's default policy blocks in public repositories
- Skip pull requests from forks under the `pull_request` trigger instead of failing


## [1.0.1] - 2026-07-05

### Fixed
- Drop unneeded content permission


## [1.0.0] - 2026-07-04

### Added
- Initial version of assign to owner workflow
