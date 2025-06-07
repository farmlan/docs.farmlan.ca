# Reproducibility

This section will provide an overview of each option's reproducibility. We will look at automation potentials and standardization.

## Automation potential

### Bare-metal deployment

Both AlmaLinux and Proxmox offer ways of an unattended installs on bare-metal. 

#### AlmaLinux

AlmaLinux utilizes [kickstart files](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/9/html/automatically_installing_rhel/kickstart-commands-and-options-reference_rhel-installer), which can be hosted by NFS, FTP, HTTP, HTTPS, or a directly by creating a custom ISO.

#### Proxmox

Proxmox utilizes [answer files](https://pve.proxmox.com/wiki/Automated_Installation) which can be fetched via HTTP or directly by creating a custom ISO. 

??? Note
    This would really only come into play if one of the hosts goes down and needs to be redeployed during the event.

### Post deployment configuration

#### AlmaLinux

AlmaLinux can be managed by cli, bash, python, ansible and many others. The method of choice would be ansible due to the amount of [community resources](https://galaxy.ansible.com/ui/) and built in [idempotency](https://docs.ansible.com/ansible/latest/reference_appendices/glossary.html#term-Idempotency).

#### Proxmox

Proxmox can be managed by anything that can interact with an API. There is an [ansible collection](https://galaxy.ansible.com/ui/repo/published/community/proxmox/docs/) for Proxmox and community made [helper scripts](https://community-scripts.github.io/ProxmoxVE/scripts) to assist with deploying VMs and LXCs.

## Standardization

### AlmaLinux

Utilizing [configuration as code (CaC)](https://unyaml.com/blog/what-is-configuration-as-code#configuration-as-code-vs-infrastructure-as-code-iac-know-the-differences) with Ansible to manage packages, compose files, server config files, and containers standardization is easily achievable.


### Proxmox

Achieving standardization with Proxmox seems a little more difficult. A mixture of Bash and Ansible could be utilized.