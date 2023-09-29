# ansible-network-configs
Use for network configuration as code and backup / restore processes.

## configs

Golden configurations for a device or set of devices. A GitHub workflow can be used to deploy the configurations via Ansible. The file name is important - `<device>.config.yml` - "device" will be passed as the limit to Ansible. 

## backups

A configuration file is maintained for each device in your inventory, with the naming convention `<inventory_hostname>.config.yml`. Anytime configurations are pulled from devices and a change is detected, Ansible will make a commit with a tag which reflects the timestamp. Configurations can be restored via the desired tag, allowing users to choose a restore point from any tagged commit made to this repo.