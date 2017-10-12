# mraerino's Workspace Config

This is an Ansible-based repository enabling me to setup my workspace machines from code.

## Usecases

- Keep environments consistent across machines
- Reinstall OS without needing a config backup
- Track workspace config changes

## Usage

### Preparations (macOS)

Run this on a blank macOS install to get up and running

```bash
xcode-select --install # Install macOS CLI utils
sudo pip install ansible # Install Ansible
git clone https://github.com/mraerino/workspace-config
cd workspace-config
```

### Execute playbook

First, create an [`inventory`](http://docs.ansible.com/ansible/latest/intro_inventory.html) file with your machines.
Then run this:

```bash
ansible-galaxy install -r requirements.yml # Install role dependencies
ansible-playbook -i inventory site.yml
```

### Inventory

The playbook uses different host groups when applying roles:

- `cli` for setting up unix cli envrionments (tested on macOS and Ubuntu)
- `macos` for configuring macOS-based systems
- `linux` for configuring Linux-based systems

Respectively there is a playbook for each of the groups.

## License

[MIT License](/LICENSE)

Feel free to adapt bits and pieces into your config.
