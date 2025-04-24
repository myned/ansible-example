# About

Example environment for Ansible automation with Cisco networking devices

Tested with:

- [Cisco 2900](https://www.cisco.com/c/en/us/products/collateral/routers/2900-series-integrated-services-routers-isr/data_sheet_c78_553896.html) router
- [Cisco Catalyst 2960](https://www.cisco.com/c/en/us/products/collateral/switches/catalyst-2960-series-switches/product_data_sheet0900aecd806b0bd8.html) switch

# Installation

### Prerequisites

- Git
- Python 3.10+
- Internet access

> [!NOTE]
> The following instructions assume Ubuntu 22.04 LTS, optionally over [WSL](https://learn.microsoft.com/en-us/windows/wsl/)

### Clone or download this repository

```sh
git clone https://github.com/myned/ansible-example
```

### Go to the project directory

```sh
cd ansible-example
```

### Install the Python venv package

> [!NOTE]
> The exact package varies depending on your distribution

```
sudo apt update
sudo apt install python3-venv
```

### Create a [Python virtual environment](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/)

```sh
python3 -m venv .venv
```

### Activate the virtual environment

```sh
source .venv/bin/activate
```

> [!TIP]
> Shells other than bash may use the relevant `activate` scripts under `.venv/bin/`

### Install dependencies within the virtual environment

```sh
pip install -r requirements.txt
```

> [!NOTE]
> Newer versions of `requirements.txt` packages may be compatible, but have not been tested

# Usage

> [!TIP]
> Example output is available in the `logs/` directory
>
> Read through each file, the comments contain additional context

### Edit inventory files as necessary

```sh
nano inventory/all.yaml
```

### Run the playbook to show configuration

```sh
ansible-playbook -i inventory/all.yaml playbooks/show-interfaces.yaml
```

### Run the playbook to modify configuration

```sh
ansible-playbook -i inventory/all.yaml playbooks/disable-interfaces.yaml
```
