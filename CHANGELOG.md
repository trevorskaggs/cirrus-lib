# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [v0.3.1] - 2020-09-27

### Changed
- output_options->collections is now optional, if not provided than item collections are not updated

### Fixed
- `process` function will reraise any error occuring while setting up processing so can be retried with redrivepolicy

## [v0.3.0] - 2020-09-02

### Changed
- Catalog.from_payload will get output payload from Batch via a separate file "<original-payload>\_out.json" rather than the original, as of Cirrus 0.2.0 Batch processes will write output to this new file rather than overwriting the input file

## [v0.2.1] - 2020-09-02

### Fixed
- Canonical link replaces previous canonical link

## [v0.2.0] - 2020-08-25

### Added
- Statedb.add_item function adds Item to DB with state=PROCESSING, must pass in Execution ARN
- Statedb.add_failed_item function adds Item to DB with state=FAILED, must pass in error message
- `process` Lambda added to consume from Cirrus Queue and start workflow (combines previous `validation` and `start-workflow` Lambdas)

### Changed
- Catalog no longer automatically adds fields as needed (e.g., a default process block, id), unless `update=True` is passed

## [v0.1.3] - 2020-08-13

### Changed
- Catalog() now sets the collection IDs of all Items based on the contents of `process->output_options->collections`. This ensures any uploaded items in any task have the correct collection

### Fixed
- Validate for collections in process['output_options'] rather than top level which always failed

## [v0.1.2] - 2020-08-10

### Changed
- No longer overwrite catalog ID if already provided

## [v0.1.1] - 2020-08-08

### Changed
- boto3-utils updated to 0.3.1

## [v0.1.0] - 2020-08-07

Initial Release

[Unreleased]: https://github.com/cirrus-geo/cirrus-lib/compare/master...develop
[v0.3.1]: https://github.com/cirrus-geo/cirrus-lib/compare/v0.3.0...v0.3.1
[v0.3.0]: https://github.com/cirrus-geo/cirrus-lib/compare/v0.2.1...v0.3.0
[v0.2.1]: https://github.com/cirrus-geo/cirrus-lib/compare/v0.2.0...v0.2.1
[v0.2.0]: https://github.com/cirrus-geo/cirrus-lib/compare/v0.1.3...v0.2.0
[v0.1.3]: https://github.com/cirrus-geo/cirrus-lib/compare/v0.1.2...v0.1.3
[v0.1.2]: https://github.com/cirrus-geo/cirrus-lib/compare/v0.1.1...v0.1.2
[v0.1.1]: https://github.com/cirrus-geo/cirrus-lib/compare/v0.1.0...v0.1.1
[v0.1.0]: https://github.com/cirrus-geo/cirrus-lib.git@0.1.0
