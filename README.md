# OSS Dev F/OSS Exploration: Phabricator and OrangeScrum

This repository contains Ansible playbooks for deploying Phabricator and OrangeScrum on OSS Dev server.


## Deploying Phabricator

The following command will deploy Phabricator on remote machine, at port :10033. Make sure Ansible are installed.

```
$ ansible-playbook playbooks/deploy_phabricator.yml -i hosts/tyranosaurus.hosts
```

You might want to install the Sprint extension too:

```
$ ansible-playbook playbooks/install_phabricator_sprint_extension.yaml -i hosts/tyranosaurus.hosts
```


## Deploying OrangeScrum

The following command will deploy OrangeScrum on remote machine, at port :10032. Make sure Ansible are installed.

```
$ ansible-playbook playbooks/deploy_orangescrum.yml -i hosts/tyranosaurus.hosts
```

You might not be able to sign in to OrangeScrum. This is a known bug. You will need to clear a MySQL table before being able to login:
```
$ sudo mysql -uroot orangescrum -e "delete from os_session_logs;"
```