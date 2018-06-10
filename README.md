# TECINI-2543-CLUS18
Various code, Ansible playbooks related to CLUS Orlando 2018 session TECINI-2543

# Explanation of Demo environment
Because of the custom Python modules that are required to be installed,
I elected to package this repository for use as a Vagrant box.  The
required Vagrantfile is included (based on CentOS 7)

# Pre-requisites
- Git (duh)
- Vagrant
- VirtualBox (for Vagrant and UCS PE)
- UCS Platform Emulator (installed into VirtualBox)

# Setup and execution

    # Boot the UCS Platform Emulator
    # Import the UCS configuration file

    # On your laptop
    git clone http://github.com/CiscoSE/TECINI-2543-CLUS18
    vagrant up
    vagrant ssh

    # In the Vagrant box (VM running in VirtualBox)
    cd TECINI-2543-CLUS18/ansible
    ansible-playbook -i hosts site.yml

