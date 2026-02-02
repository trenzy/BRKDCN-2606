# Repository Ansible code/configuration for Cisco Live breakout session BRKDCN-2606

This repository is built to support the Cisco Live breakout session BRKDCN-2606. This repository contains 4 separate directories with an Ansible Role.

- 1 `access_policies` which configures ACI Fabric access policies for both end points (and EPGs) in our Tenant as well as for an L3Out which will be used to connect to an upstream NX-OS device

- 2 `tenant` which provisions a ACI Tenant and associated child policies (VRF, Bridge-Domain, BD Subnet, etc.)

- 3 `L3Out` which provisions an L3Out to an external NX-OS switch to show reachability from a host in the Tenant.

- 4 `static_path` which configures the static path bindings for the hosts in the newly created Tenant and EPG.

This was developed and tested with Ansible version 2.18.4 and latest version of the Ansible ACI collection (2.10.1 at the time this was developed).

If you plan to modify this code as the environment this was developed and run on may be different than what you want to run this playbook against.


## Installing Ansible

To install Ansible, please visit the following [site](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).

It is recommended to use a virtual environment with Ansible if running it on a local system.

## Clone this git repository

You will need to have Git installed on your system. If you don't have it installed, you can download it from [here](https://git-scm.com/downloads). To clone the repository, run the following command:

```bash
git clone https://github.com/trenzy/BRKDCN-2606
```

## Running Ansible 

If you don't have it installed, you should download the latest ACI collection from Ansible Galaxy:

```bash
ansible-galaxy collection install cisco.aci
```

To run this Ansible playbook, you first need to set the Environment Variable from the OS for authentication and the APIC IP:

```bash
export APIC_USERNAME=<username>
export APIC_PASSWORD=<password>
export APIC_IP=<password>
```

Then run your Ansible playbook against your target system:

```bash
ansible-playbook -i hosts.ini main.yml
```

During the session, I should a couple of packet captures that highlight the differences between regular username/password and HTTP API (which is what is configured here). You can view those in Wireshark and they are located in the `packet_captures` directory.