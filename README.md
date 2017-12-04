# Ansible LDAP Server

This is a Ansible role to install OpenLDAP Client (support Ubuntu16.04 / Centos7)

## Requirements

Ansible 2.1

## Role Variables

|Variable|Default Value|Description|
|---|---|---|
```dc_string```|dc=example,dc=com|domain components string.
```ldap_user_id```|ldapuser|ldap default user.
```ldap_server_list```|["127.0.0.1"]|ldap server list.

## Example
```
### create a requirements.yml
- src: git+https://github.com/willyhutw/ansible-role-ldap-client.git
  name: ldap-client

### create a playbook.yml
- hosts: all
  become: yes
  roles:
    - roles/ldap-client

### install this role
ansible-galaxy install -r requirements.yml -p ./roles

### run it!
ansible-playbook -i '192.168.33.142,' playbook.yml \
-e "ansible_ssh_user=vagrant ansible_ssh_pass=vagrant" \
-e "dc_string=dc=my-domain,dc=com ldap_user_id=willyhu" \
-e '{"ldap_server_list":["192.168.33.141"]}'
```

## License

MIT / BSD

## Author Information

willyhu.tw@gmail.com

