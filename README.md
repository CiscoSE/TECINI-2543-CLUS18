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

# Finalizing the UCS Platform Emulator
After importing the OVA but prior to booting the emulator, you must configure the
three network adapters on the VM to connect to a network that provides DHCP 
addresses.

In VirtualBox, you'll have to create a Host Network first via the "Host Network Manager".
On a Mac, the manager is found in the File menu:

!(images/host-ntwk-mgr.png)

In the manager, click the "Create" button to create a new host network.  Ensure the IP 
network does not overlap the 192.168.254.0/24 network as that will cause conflicts with
the IP Management pool created by the Ansible playbook in this demo.

!(images/create-host-network.png)

Close the Host Network Manager and edit the UCSPE VM settings.  Under the Network 
settings of the VM, for Adapters 1-3, change the "Attached To" setting to 
"Host-only Adapter" and ensure the "Name" setting matches the host network you created.

!(https://github.com/CiscoSE/TECINI-2543-CLUS18/blob/master/images/convert-adapter-host-only.png)

Now, the UCS Platform Emulator is ready to boot.

Once booted, load the core policy configuration from the XML in the ''ucspe'' 
directory

# Setup and execution

    # After the UCSPE is booted and XML loaded

    # On your laptop
    git clone http://github.com/CiscoSE/TECINI-2543-CLUS18
    vagrant up
    vagrant ssh

    # In the Vagrant box (VM running in VirtualBox)
    cd TECINI-2543-CLUS18/ansible
    ansible-playbook -i hosts site.yml

