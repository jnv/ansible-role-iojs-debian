# io.js Ansible Role for Debian and Ubuntu

Setup [io.js](https://iojs.org/) repository and install binary package [provided by Nodesource](https://nodesource.com/blog/nodejs-v012-iojs-and-the-nodesource-linux-repositories).

## Deprecated

Use [nodesource.node](https://github.com/nodesource/ansible-nodejs-role) role provided by Nodesource.

## Supported Distributions

Only the latest versions of Ubuntu and Debian are supported by Nodesource.

Ubuntu since version 14.04 (trusty).

Debian since Jessie.

## Requirements

The role uses [apt_repository module](http://docs.ansible.com/apt_repository_module.html) which has additional dependencies. You can use [bootstrap-debian](https://github.com/cederberg/ansible-bootstrap-debian) role to setup common Ansible requirements on Debian-based systems.

Furthermore the repository uses HTTPS, so make sure package `apt-transport-https` is available on your system.

## Role Variables

- `iojs_version`: Version of the io.js package to install.
    - Default: `"1.8.*"`
    - **Note**: Package version contains suffix, so make sure to always end the version specification with asterisk, e.g. `1.8.1*`
- `iojs_repo_base`: Base URL for the package repository.
    - Default: `"https://deb.nodesource.com/iojs_1.x"`
- `iojs_repo_key_url`: Repository GPG key to install.
    - Default: `"https://deb.nodesource.com/gpgkey/nodesource.gpg.key"`
- `iojs_repo_key_id`: ID of the GPG key to be installed to prevent needless download.
    - Default: `"1655A0AB68576280"`

## Example Playbook

    - hosts: servers
      roles:
         - { role: jnv.iojs-debian }

## License

[![CC0 Public Domain](http://i.creativecommons.org/p/zero/1.0/88x31.png)](http://creativecommons.org/publicdomain/zero/1.0/)
