# TECINI-2543-CLUS18
Various code, Ansible playbooks related to CLUS Orlando 2018 session TECINI-2543

# Explanation of Demo environment
Because of the custom Python modules that are required to be installed,
I elected to package this repository for use as a Vagrant box.  The
required Vagrantfile is included (based on CentOS 7)

# Pre-requisites
- Git
  - https://git-scm.com/
- Vagrant
  - https://www.vagrantup.com/
- VirtualBox (for Vagrant and UCS PE)
  - https://www.virtualbox.org/
- UCS Platform Emulator (installed into VirtualBox)
  - https://communities.cisco.com/docs/DOC-71877

# Configuration
- UCSPE configuration found [here](ucspe/README.md)

# Setup and execution

    # After the UCSPE is booted and XML loaded

    # On your laptop
    git clone http://github.com/CiscoSE/TECINI-2543-CLUS18
    vagrant up
    vagrant ssh

    # In the Vagrant box (VM running in VirtualBox)
    cd TECINI-2543-CLUS18/ansible

    # Correct the UCSPE IP address in host_vars/ucspe.yml

    # Run the playbook
    ansible-playbook -i hosts site.yml

