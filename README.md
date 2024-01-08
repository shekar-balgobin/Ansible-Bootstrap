# Ansible Bootstrap

## Overview

``` mermaid
flowchart
    subgraph GR[Git Repository]
    end

    subgraph ACN[Ansible Control Node]
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

- Update OS.

```sudo apt update```
```sudo apt upgrade```

enter yes

- Install Ansible.

```sudo apt install ansible```

enter yes

- Install Git.

```sudo apt install git```

enter yes

- Create Git user.

```ssh-keygen -t ed25519 -C ansible-control-node```

enter 3 times

Open ~/.ssh/ed25519.pub and copy the public key to the clipboard.
Add this key to GitHub.

- Clone Ansible bootstrap repository.
_Note: This step may be deleted once Ansible pull comes into play_

```git clone git@github.com:shekar-balgobin/Ansible-Bootstrap.git```

