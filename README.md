![Logo](https://raw.githubusercontent.com/idealista/php_role/master/logo.gif)

# PHP Ansible role

[![Build Status](https://travis-ci.org/idealista/php_role.png)](https://travis-ci.org/idealista/php_role)

This Ansible role installs PHP (optionally, with FPM enabled) in a Debian environment.

- [Getting Started](#getting-started)
	- [Prerequisities](#prerequisities)
	- [Installing](#installing)
- [Usage](#usage)
- [Testing](#testing)
- [Built With](#built-with)
- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)
- [Contributing](#contributing)

## Getting Started

These instructions will get you a copy of the role for your Ansible playbook. Once launched, it will install [PHP](https://secure.php.net/) in a Debian system.

### Prerequisities

Ansible >= 2.9.x.x version installed.
Inventory destination should be a Debian environment.

For testing purposes, [Molecule](https://molecule.readthedocs.io/) (version 3.x) with [Docker](https://www.docker.com/) as provider.

### Installing

Create or add to your roles dependency file (e.g requirements.yml):

``` yml
- src: idealista.php_role
  version: 1.3.0
  name: php
```

Install the role with ansible-galaxy command:

```
ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

``` yml
---
- hosts: someserver
  roles:
    - role: php
```

## Usage

Look to the [defaults](defaults/main.yml) properties file to see all possible configuration properties.

## Testing

First, we initialize a virtualenv:
```
pipenv shell
pipenv sync
```

To test all possible scenarios:
```
molecule test --all
```

To test default scenario (bare installation, no FPM):
```
molecule test -s default
```

To test FPM installed scenario:
```
molecule test -s fpm
```

## Built With

![Ansible](https://img.shields.io/badge/ansible-2.9.9-green.svg)
![Molecule](https://img.shields.io/badge/molecule-3.0.4-green.svg)
![Goss](https://img.shields.io/badge/goss-0.3.13-green.svg)

## Versioning

For the versions available, see the [tags on this repository](https://github.com/idealista/php_role/tags).

Additionaly you can see what change in each version in the [CHANGELOG.md](CHANGELOG.md) file.

## Authors

* **Idealista** - *Work with* - [idealista](https://github.com/idealista)

See also the list of [contributors](https://github.com/idealista/php_role/contributors) who participated in this project.

## License

![Apache 2.0 Licence](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.

## Contributing

Please read [CONTRIBUTING.md](.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.
