# Snapcast Server

[![License: MIT](https://img.shields.io/github/license/stegmannb/ansible-role-snapserver)](https://github.com/stegmannb/ansible-role-snapserver/blob/master/LICENSE)
![Continuous Integration](https://github.com/stegmannb/ansible-role-snapserver/workflows/Continuous%20Integration/badge.svg)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)

## Requirements

To execute this role the [jmespath](https://pypi.org/project/jmespath/) package is required on the host machine.
You can install it with `pip install jmespath`.

## Role Variables

- `snapserver_update`: If `True` updates an existing snapserver package to the newest version from GitHub. (Default `True`)
- `snapserver_rpc_port`: The port Snapserver listens on. (Default `1705`)
- `snapserver_dirs_to_create`: (Default []) Create these directories before starting the snapcast server.
- `snapserver_sources`: (Default []) List of sources for the snapcast server 
- `snapserver_runtime_directory`: (Default snapserver) Runtime directory for the systemd service. [man systemd](https://www.freedesktop.org/software/systemd/man/systemd.exec.html#RuntimeDirectory=)

## Dependencies

This role requires the [community.general collection](https://galaxy.ansible.com/community/general?extIdCarryOver=true&sc_cid=701f2000001OH7YAAW).

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: server

      vars:
        snapserver_sources:
          - pipe:///tmp/audio/default?name=Pipe&mode=create&dryout_ms=2000

      roles:
         - role: stegmannb.snapcast_server

## License

MIT
