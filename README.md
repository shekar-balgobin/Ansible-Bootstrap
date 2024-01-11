# Ansible Bootstrap

## Overview

``` mermaid
flowchart
    subgraph GR[Git Repository]
    end

    subgraph ACN[Ansible Control Node]
        A[Ansible]
        G[Git]
    end

    subgraph MN0[Managed Node 0]
    end

    subgraph MN1[Managed Node 1]
    end

    subgraph MNN[Managed Node n]
    end

    ACN-->MN0
    ACN-->MN1
    ACN-->MNN
    GR---ACN
```

## Ansible Control Node

- Establish a secure connection with ```ssh user@hostname```, ```yes``` to continue connecting, followed by the password.

- Update the package index with ```sudo apt update```.

- Install the packages with ```sudo apt upgrade```, followed by ```Y``` to continue.

### Ansible

- Install Ansible with ```sudo apt install ansible```, followed by ```Y``` to continue.

#### SSH Key for Ansible User

- Generate the SSH key for the Ansible user with ```ssh-keygen -t ed25519 -C ansible-user```

### Git

- Install Git with ```sudo apt install git```, followed by ```Y``` to continue.



---

- Create Git user.

```ssh-keygen -t ed25519 -C ansible-control-node```

enter 3 times

Open ~/.ssh/ed25519.pub and copy the public key to the clipboard.
Add this key to GitHub.

- Clone Ansible bootstrap repository.
_Note: This step may be deleted once Ansible pull comes into play_

```git clone git@github.com:shekar-balgobin/Ansible-Bootstrap.git```

