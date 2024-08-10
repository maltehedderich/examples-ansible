# Ansible Playbooks

## What is Ansible?

Ansible is an open-source automation tool that simplifies configuration management, application deployment, and task automation. It uses a declarative language to describe system configurations and can manage multiple systems simultaneously.

Key features of Ansible:

- **Agentless**: No need to install software on managed nodes
- **YAML-based**: Uses simple, human-readable YAML files for playbooks
- **Idempotent**: Can safely run playbooks multiple times without changing the result
- **Extensible**: Supports modules and plugins for extended functionality

## Prerequisites

- Ansible installed on your local machine
- SSH access to the targets (e.g., VPS, servers)
- Basic understanding of YAML and Linux commands

## Installation

To install Ansible on your local machine:

### Ubuntu/Debian:

```bash
sudo apt update
sudo apt install ansible
```

### macOS (using Homebrew):

```bash
brew install ansible
```

### Windows (using WSL):

Install Windows Subsystem for Linux (WSL) and then install Ansible within the Linux environment.
Verify the installation:

```bash
ansible --version
```

## Running the Playbooks

1. Create an inventory file (e.g., inventory.ini) with your VPS details:

```text
[vps]
your_vps_name ansible_host=your_vps_ip ansible_user=root
```

2. Ensure SSH key-based authentication is set up:

```bash
ssh-copy-id -i ~/.ssh/your_key.pub root@your_vps_ip
```

3. Run the playbook:

```bash
ansible-playbook -i inventory.ini <PATH_TO_PLAYBOOK>
```

## Customization

- Modify the vars section in the playbook to customize settings like SSH port and username.
- Add or remove tasks as needed for your specific requirements.

## Best Practices

- Always test playbooks in a non-production environment first.
- Use version control (e.g., Git) to track changes to your playbooks.
- Regularly update and review your security measures.
- Use Ansible Vault for sensitive information.

## Troubleshooting

- If you encounter SSH issues, ensure your SSH key is correctly set up and the VPS is reachable.
- Check Ansible logs for detailed error messages.
- Verify that the playbook YAML syntax is correct.

## Additional Resources

- [Ansible Documentation](https://docs.ansible.com/)
- [Ansible Best Practices](https://docs.ansible.com/ansible/latest/tips_tricks/ansible_tips_tricks.html)
- [Ansible Galaxy](https://galaxy.ansible.com/)
