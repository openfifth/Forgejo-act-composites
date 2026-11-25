# Forgejo-act-composites

This repository contains a set of ACT composites we share across our workflows

### init_kdd_env

Initialises tmp directories and env vars for Koha-dpkg-docker to use

Usage in workflows:

```
---
name: Fully test, build, and publish Koha code

on:
  push:
  workflow_call:
  workflow dispatch:

jobs:
  execute_kdd:
    name: Execute k.d.d run
    if: ${{ !cancelled() }}
    runs-on:
      - trixie
      - lxc
    steps:
      - name: Initialise k.d.d environment
        uses: https://forgejo.openfifth.co.uk/openfifth/Forgejo-act-composites/init_kdd_env@trunk
```

### install_docker_ce

Installs standalone Docker CE Daemon and CLI

Usage in workflows:

```
---
name: Fully test, build, and publish Koha code

on:
  push:
  workflow_call:
  workflow dispatch:

jobs:
  install_docker_ce:
    name: Install Docker CE and exit
    if: ${{ !cancelled() }}
    runs-on:
      - trixie
      - lxc
    steps:
      - name: Install Docker CE
        uses: https://forgejo.openfifth.co.uk/openfifth/Forgejo-act-composites/install_docker_ce@trunk
```
