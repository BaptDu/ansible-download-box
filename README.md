# Ansible Download Box

Allows, depending on the configuration, to automate the configuration of the server and install everything needed for its commissioning.

## Credit

------------

All the part of the docker-composer was taken from **Sebastien GUILLOUX** _alias_ [@sebgl](https://github.com/sebgl) don't hesitate to have a look around to see the configuration, which is much better explained in his [project](https://github.com/sebgl/htpc-download-box) !!!

## Prerequisite

------------

```bash
python get-pip.py
python -m pip install ansible
```

## Disclaimer

------------

**I do not encourage or support hacking, it is for information and learning purposes only.**

## Requirements

------------
To simplify the connection between ansible is your server you can execute this command

```bash
 ssh-copy-id -i [path_for_key_id_rsa] [username]@[server_ip]
```

For the proper functioning of the role, you will have to create a `hosts.yml` and `playbook.yml` file and copy the information from `hosts.example.yml` , `playbook.example.yml` and fill in the information in it.

## Hosts Variables

------------

```yml
all:
  hosts:
    name_for_serveur:
      ansible_host: ip for host
      ansible_port: number for host
      ansible_user: user for host
      ansible_ssh_private_key_file: path for key id_rsa (optional)
      ansible_python_interpreter: /usr/bin/python3
      ansible_sudo_pass: password sudo for execute command
    # ...
```

## Playbook Variables

------------

```yml
- hosts: name_for_serveur
  roles:
    - dependencies
    - role : docker
```

## Launch ansible

------------

```bash
ansible-playbook -i hosts.yml playbook.yml
```

## Author Information

------------

* **DUMONT Baptiste** _alias_ [@BaptDu](https://github.com/BaptDu)
