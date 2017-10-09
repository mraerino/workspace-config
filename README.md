# mraerino's Workspace Config

This is an Ansible-based repository enabling me to setup my workspace machines from code.

## Usecases

- Keep environments consistent across machines
- Reinstall OS without needing a config backup
- Track workspace config changes

## Usage

First, create an [`inventory`](http://docs.ansible.com/ansible/latest/intro_inventory.html) file with your machines.
Then run this:

```bash
ansible-playbook -i inventory site.yml
```

*Notice: You obviously need to have [Ansible](https://www.ansible.com/) installed*

### Inventory

The playbook uses different host groups when applying roles:

- `cli` for setting up unix cli envrionments (tested on macOS and Ubuntu)
- `macos` for configuring macOS-based systems
- `linux` for configuring Linux-based systems

Respectively there is a playbook for each of the groups.

## License

[MIT License](/LICENSE)

Feel free to adapt bits and pieces into your config.