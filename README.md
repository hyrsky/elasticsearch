# Elasticsearch server

## Install

```shell
$ ansible-playbook playbook.yml -i hosts --ask-vault-pass
```

## Requirements
 * [ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Edit

Configuration is stored in `vars/config.yml` and `vars/vault.yml`. Configuration stored in vault contain credentials so the file is encrypted. Edit vault with:
```shell
$ ansible-vault edit vars/vault.yml
```

## Adding and Updating Galaxy roles

From time to time, third party roles need to be added or updated to enable new
functionality or fix bugs. To update a role find the role's version setting
inside requirements.yml, bump the version to the required or latest version
of the role, then run the following command in the
same directory as this README file:

```shell
$ ansible-galaxy install -r requirements.yml --force
```

Then commit the updated requirements.yml file and the new and updated files
within the roles directory.
