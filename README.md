# ansible-role-optimization-max-open-files

Ansible role for setting max open files on Linux host. This rile sets correct values in:

* /etc/security/limits.conf
* /etc/sysctl.conf

### Prerequisites

* Make sure that you understand what the variables in the settings do. Make sure that you set your limits in
the corresponding systemd configuration for the services which you want to have these limits set to. This role
will not do that. Example configuration for systemd services:

```
LimitNOFILE=2097152
LimitNPROC=2097152
```

### Supported OS

* All

## Deployment

Example playbook named optimization-max-open-files.yml:

```
- hosts: web
  roles:
    - 'ansible-role-optimization-max-open-files'
```

Configure your vars in vars/main.yml. After that simply run your playbook:

```
ansible-playbook -i '<TARGET_HOST_IP>,' playbooks/optimization-max-open-files.yml
```

## Minimal Ansible version

* 2.0

## Built With

* [Ansible 2.8](https://docs.ansible.com/ansible/2.8/index.html)

## Authors

* **Valentin Dzhorov** - *Initial work* - [vdzhorov](https://github.com/vdzhorov)

## Company

* **Delta.BG**

## License

This project is licensed under the MIT License.
