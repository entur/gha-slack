# Changelog

## [3.1.0](https://github.com/entur/gha-slack/compare/v3.0.1...v3.1.0) (2026-03-23)


### Features

* emoji react to messages and able to post to threads ([#43](https://github.com/entur/gha-slack/issues/43)) ([e104ab5](https://github.com/entur/gha-slack/commit/e104ab5e92f64daadba1a0033fc8d925b7b66017))
  ⚠️ Reacting to slack messages needs new "react write" permissions, please renew permissions with `/invite github actions` in your slack channel.

## [3.0.1](https://github.com/entur/gha-slack/compare/v3.0.0...v3.0.1) (2026-03-09)


### Bug Fixes

* prevent shell injection by using intermediate env vars ([#39](https://github.com/entur/gha-slack/issues/39)) ([fa7909f](https://github.com/entur/gha-slack/commit/fa7909f2c3ef76bfbd28ecf9aa6af676c91c1ff8))

## [3.0.0](https://github.com/entur/gha-slack/compare/v2.0.2...v3.0.0) (2025-11-19)


### ⚠ BREAKING CHANGES

* Bump slack-github-action to version 2.
* blocks input must be a json array, see slack block kit for reference.

### Features

* Bump slack-github-action to version 2 ([#30](https://github.com/entur/gha-slack/issues/30)) ([c376aed](https://github.com/entur/gha-slack/commit/c376aed5633174716a667f1d0c38d323ad35689f))
* Bump slack-github-action to version 2. ([c376aed](https://github.com/entur/gha-slack/commit/c376aed5633174716a667f1d0c38d323ad35689f))


### Bug Fixes

* new common standard dependabot config [skip ci] ([#26](https://github.com/entur/gha-slack/issues/26)) ([4c08f74](https://github.com/entur/gha-slack/commit/4c08f741deec0b4998798202073ebb06dce1dd54))

## [2.0.2](https://github.com/entur/gha-slack/compare/v2.0.1...v2.0.2) (2024-11-05)


### Bug Fixes

* typo and link ([c4848c2](https://github.com/entur/gha-slack/commit/c4848c2a77c33657212697f13a83657d03fc3f55))

## [2.0.1](https://github.com/entur/gha-slack/compare/v2.0.0...v2.0.1) (2024-09-25)


### Bug Fixes

* allow line break in simple message ([#17](https://github.com/entur/gha-slack/issues/17)) ([162fd9c](https://github.com/entur/gha-slack/commit/162fd9c6ef2c7dcc266a90c5ba0a303a8c30f4cd))

## [2.0.0](https://github.com/entur/gha-slack/compare/v1.0.1...v2.0.0) (2024-09-03)


### ⚠ BREAKING CHANGES

* add functionality to send messages and blocks ([#14](https://github.com/entur/gha-slack/issues/14))

### Features

* add functionality to send messages and blocks ([#14](https://github.com/entur/gha-slack/issues/14)) ([cbd3397](https://github.com/entur/gha-slack/commit/cbd339738efb4ae5557d07c263f9a14085eea306))

## [1.0.1](https://github.com/entur/gha-slack/compare/v1.0.0...v1.0.1) (2024-05-23)


### Bug Fixes

* set timeout ([#11](https://github.com/entur/gha-slack/issues/11)) ([be4c794](https://github.com/entur/gha-slack/commit/be4c79403ca7c439d253f7d1a469d5db9a4937b3))
* use sandbox channel ([b7ac51a](https://github.com/entur/gha-slack/commit/b7ac51a69e8561ee687d0534314b87e0a4d08d1b))

## 1.0.0 (2024-04-26)


### Features

* initial version ([46e4dbd](https://github.com/entur/gha-slack/commit/46e4dbd2790cfbd88a9fe60bfb3b60a7aeec1cef))
* initial version ([5d54ba2](https://github.com/entur/gha-slack/commit/5d54ba23401ca958b187d6a22cbbf41e4a311001))


### Bug Fixes

* escape code for image ([c45056c](https://github.com/entur/gha-slack/commit/c45056c67352b5280cff00aecf4f629b39397e37))
* use payload ([0fca4a2](https://github.com/entur/gha-slack/commit/0fca4a2669ff3aff3dcf61521012e3866840ab13))
