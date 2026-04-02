# mk_inet4031_puppet_lab11
Puppet code from INET 4031 Lab 11 - Configuration as Code (CaC).

## Overview
This project demonstrates using Puppet to automate system configuration on an Ubuntu 24.04 server. It includes managing users/groups and deploying a full LAMP stack (Linux, Apache, MySQL/MariaDB, PHP).

## Features

### User & Group Management
- Created groups: `group01`, `group02`
- Created users:
  - user04 (group01)
  - user05 (group02)
  - user06 (group01, group02)
  - user07 (no group)
- Enforced:
  - user existence
  - home directories
  - secure (hashed) passwords

### LAMP Stack Deployment
- Apache2 web server installed and running
- PHP installed with modules:
  - libapache2-mod-php
  - php-cli
  - php-mysql
- MariaDB (MySQL) installed and running
- Apache enabled at boot

### PHP Test Page
- Deployed `phpinfo.php` using Puppet
- Verified PHP functionality via browser

## Files

- `lamp_stack_server.pp` → Defines LAMP stack role
- `phpinfo.php` → Test file for PHP
- `server_users_groups.pp` → Manages users and groups
- `testing_puppet.pp` → Creates a test file to verify Puppet functionality

## How to Apply

Run Puppet manifests:

```bash
sudo puppet apply server_users_groups.pp
sudo puppet apply lamp_stack_server.pp
