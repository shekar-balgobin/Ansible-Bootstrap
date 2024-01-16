# Ansible Bootstrap

``` mermaid
C4Context
    title Container Diagram: The Ansible bootstrap process

    System_Ext(GH, "GitHub")

    Boundary(B, "") {
        Container(ACN, "Absible Control Node", "Automation Platform", "Periodically execute playbook")

        Deployment_Node(DN, "", "") {
            Container(MN0, "Managed Node 0")
            Container(MN1, "Managed Node 1")
            Container(MNN, "Managed Node n")
        }
    }

    Rel(ACN, MN0, "Execute playbook")
    Rel(ACN, MN1, "Execute playbook")
    Rel(ACN, MNN, "Execute playbook")
    Rel(ACN, GH, "Pull playbook")
```

## Overview

__Ansible Bootstrap__ is an automated process that periodically executes an Ansible playbook to synchronise a set of nodes to a desired state as shown in the diagram above.

The __Ansible Control Node__ (ACN) uses ```ansible-pull``` to get a copy of the playbook from [__GitHub__](https://github.com/). This is executed continuously to synchronise the set of managed nodes (MN).

This document details how to set up such a process.

### What You'll Need

- A Raspberry Pi designated as an ACN
- A set of one or preferably more Raspberry Pis designated as MN
- A [GitHub repository](https://github.com/shekar-balgobin/Ansible-Bootstrap.git) hosting the playbook

## Ansible Control Node

- Establish a secure connection to the ACN.

- Update the package index with ```sudo apt update```.

- Install the packages with ```sudo apt upgrade```, followed by ```Y``` to continue.

### Ansible

- Install Ansible with ```sudo apt install ansible```, followed by ```Y``` to continue.

### Git

- Install Git with ```sudo apt install git```, followed by ```Y``` to continue.

### Clone the Repository

- Clone the bootstrap repository with ```git clone https://github.com/shekar-balgobin/Ansible-Bootstrap.git```, followed by 'yes' to cintinue.
- Change directory with ```cd Ansible-Bootstrap```.