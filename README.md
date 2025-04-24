# About

Example environment for Ansible automation with Cisco networking devices

Tested with:

- [Cisco 2900](https://www.cisco.com/c/en/us/products/collateral/routers/2900-series-integrated-services-routers-isr/data_sheet_c78_553896.html) router
- [Cisco Catalyst 2960](https://www.cisco.com/c/en/us/products/collateral/switches/catalyst-2960-series-switches/product_data_sheet0900aecd806b0bd8.html) switch

# Installation

### Prerequisites

- Git
- Python 3

> [!NOTE]
> The following instructions assume Ubuntu 22.04 LTS, optionally over [WSL](https://learn.microsoft.com/en-us/windows/wsl/)

### Clone or download this repository

```sh
git clone https://github.com/myned/ansible-example
```

### Go to project directory

```sh
cd ansible-example
```

### Create virtual environment

```sh
python3 -m venv .venv
```

### Activate virtual environment

```sh
source .venv/bin/activate
```

> [!TIP]
> Shells other than bash may use the relevant `activate` scripts under `.venv/bin/`

### Install dependencies

```sh
pip install -r requirements.txt
```

> [!NOTE]
> Newer versions of `requirements.txt` packages may be compatible, but have not been tested

# Usage

> [!NOTE]
> Example output is available in the `logs/` directory

### Edit inventory files as necessary

```sh
nano inventory/all.yaml
```

### Run playbook to show all interfaces

```sh
ansible-playbook -i inventory/all.yaml playbooks/show-interfaces.yaml
```

### Run playbook to modify configuration by disabling interfaces

```sh
ansible-playbook -i inventory/all.yaml playbooks/disable-interfaces.yaml
```
