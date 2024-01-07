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

    subgraph MNN[Managed Node N]
    end

    ACN-->MN0
    ACN-->MN1
    ACN-->MNN
    GR---ACN
```

## Ansible Control Node

-

```sudo apt update```
```sudo apt upgrade```

enter yes

- 
```sudo apt install ansible```

enter yes