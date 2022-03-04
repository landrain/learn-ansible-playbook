## Ansible Depedencies
This ansible files will help engineer to automate the process of Installing and Configuring depedencies

### Usage
1) Edit `ansible.cfg` to meet the criteria
2) Edit `hosts.ini` to add an inventory for remote host
3) Set variable of each depedency in `ansible/group_vars/*`
4) Install ansible collection & roles by run this command `ansible-galaxy collection install -r requirements.yml`
5) After all set, you can start setup by run `ansible-playbook setup.yml`

### Setup Case
If you want to run only specific node, you can add `--tags` flag. Example if you want to just run setup & config for redis, mysql and mongo. Just run :

`ansible-playbook setup.yml --tags "redis,mysql,mongo"`

Also you can skip configuration / node by adding `--skip-tags` flag. Example if you want to skip setup & config for kubernetes and kudu. Just run :

`ansible-playbook setup.yml --skip-tags "kubernetes.kudu"`