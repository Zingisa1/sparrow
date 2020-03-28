+++
title = "Installation"

date = 2020-01-02
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.
weight = 30
+++
## Requirements
* Your hardware runs a minimal rasbian (or equivalent), installed with UTF8 locales
* The network of this computer is correctly configured and it has internet access

## Installation

#### 1. Install required packages
```bash
apt install -y ansible git
```

#### 2. Clone repo containing ansible recipes for the Wazo Platform
```bash
git clone https://github.com/benasse/wazo-ansible/
```

#### 3. Configure your application password
```bash
cd wazo-ansible
```
* Edit the file `inventories/uc-engine` with your favorite text editor
* Add the following lines at the end of the file, replacing `****` with your password
```
engine_api_configure_wizard = true
engine_api_root_password = ****
```
#### 4. Install ansible dependency
```bash
ansible-galaxy install -r requirements-postgresql.yml
```
#### 5. Start installation
```bash
ansible-playbook -i inventories/uc-engine uc-engine.yml
```
If you get an error please refer on the troubleshooting part of the documentation.
#### 6. Login to wazo-ui
Wazo-ui is available on port `443` of your engine, you can access it via an internet browser.
Use `root` as login and the password that you defined at the start of the installation.
