# Pre-requisite Policy Setup
- Boot Policy
  - "PXE:CIMC:LUN"
- Maintenance Policy (UserAck)
  - "UserAck:NoBoot"
- BIOS Policy (VT and/or Performance, usNIC required settings)
  - "HPC:Compute"
- Local Disk Policy (RAID1)
  - "RAID1:Protect"
- Scrub Policy
  - "Disk:Bios:NoFlex"

# Post Ansible Configuration Steps
- usNIC Connection Policy (number of usNICs)
- Enable usNIC on usNIC vNIC template interfaces, assign policy

# Optional post-Ansible steps
- Network Control Policy, Assign to vNIC templates
