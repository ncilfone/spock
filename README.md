[![Spock](https://raw.githubusercontent.com/fidelity/spock/master/resources/images/logo.png)](https://fidelity.github.io/spock/)
> Managing complex configurations any other way would be highly illogical...

[![License](https://img.shields.io/badge/License-Apache%202.0-9cf)](https://opensource.org/licenses/Apache-2.0)
[![Python](https://img.shields.io/badge/python-3.6+-informational.svg)]()
[![PyPI version](https://badge.fury.io/py/spock-config.svg)](https://badge.fury.io/py/spock-config)
[![Coverage Status](https://coveralls.io/repos/github/fidelity/spock/badge.svg?branch=master)](https://coveralls.io/github/fidelity/spock?branch=master)
![Tests](https://github.com/fidelity/spock/workflows/pytest/badge.svg?branch=master)
![Docs](https://github.com/fidelity/spock/workflows/docs/badge.svg)

## About

`spock` is a framework that helps manage complex parameter configurations during research and development of Python 
applications. `spock` lets you focus on the code you need to write instead of re-implementing boilerplate code like 
creating ArgParsers, reading configuration files, implementing traceability etc.

In short, `spock` configurations are defined by simple and familiar class-based structures. This allows `spock` to 
support inheritance, read from multiple markdown formats, and allow hierarchical configuration by composition.

## Quick Install

Requires Python 3.6+

```bash
pip install spock-config
```

w/ S3 extension

```bash
pip install spock-config[s3]
```

## Version(s)

All prior versions are available on PyPi. If legacy API and backend support is needed please install a pre v2.0.0+ 
version. We recommend refactoring your code to the new API and backend instead as legacy versions will be missing 
recent features, bugfixes, and hotfixes.

* v2.0.0+: Dropped support for legacy backend and API semantics
* v1.1.0-v1.2.1: New API with support for legacy backend and legacy API semantics
* v1.0.0: Legacy API and backend 

## News

See [Releases](https://github.com/fidelity/spock/releases) for more information.

#### May 6th, 2021
* Added S3 support with `pip install spock-config[s3]`
* S3 addon supports automatically handling loading/saving from paths defined with `s3://` URI(s) by passing in an
active `boto3.Session`

#### March 18th, 2021

* Support for Google docstring style annotation of `spock` class (and Enums) and attributes
* Added in ability to print docstring annotated help information to command line with `--help` argument

## Documentation

Current documentation and more information can be found [here](https://fidelity.github.io/spock/).

Example `spock` usage is located [here](https://github.com/fidelity/spock/blob/master/examples).

## Key Features

* [Simple Declaration](basic_tutorial/Define.md): Type checked parameters are defined within a `@spock` decorated 
  class. Supports required/optional and automatic defaults.
* Easily Managed Parameter Groups: Each class automatically generates its own object within a single namespace.
* [Parameter Inheritance](advanced_features/Inheritance.md): Classes support inheritance allowing for complex 
  configurations derived from a common base set of parameters.
* [Complex Types](advanced_features/Advanced-Types.md): Nested Lists/Tuples, List/Tuples of Enum of `@spock` classes, 
  List of repeated `@spock` classes
* Multiple Configuration File Types: Configurations are specified from YAML, TOML, or JSON files.
* [Hierarchical Configuration](advanced_features/Composition.md): Compose from multiple configuration files via 
  simple include statements.
* [Command-Line Overrides](advanced_features/Command-Line-Overrides.md): Quickly experiment by overriding a value with 
  automatically generated command line arguments.
* Immutable: All classes are *frozen* preventing any misuse or accidental overwrites (to the extent they can be in 
  Python).
* [Tractability and Reproducibility](basic_tutorial/Saving.md): Save runtime parameter configuration to YAML, TOML, 
  or JSON with a single chained command (with extra runtime info such as Git info, Python version, machine FQDN, 
  etc). The saved markdown file can be used as the configuration input to reproduce prior runtime configurations.
* [S3 Addon](addons/S3.md): Automatically detects `s3://` URI(s) and handles loading and saving `spock` configuration 
  files when an active `boto3.Session` is passed in (plus any additional `S3Transfer` configurations)

#### Main Contributors

[Nicholas Cilfone](https://github.com/ncilfone), [Siddharth Narayanan](https://github.com/sidnarayanan)
___
`spock` is developed and maintained by the **Artificial Intelligence Center of Excellence at Fidelity Investments**.

