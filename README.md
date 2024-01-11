# Ansible Role: drupal.docker

A full list of defaults and their values can be found in the `defaults/main.yml`.

Author : Alexander Aguilar
email  : alexolomeo@gmail.com

## host file

```yml

[drupalserver]
localhost

[drupalserver:vars]
ansible_user=ubuntu
#ansible_become=yes
#ansible_become_method=sudo
#ansible_port= 2244
ansible_ssh_private_key_file= ./KEY-UBUNTU

```

## Example Playbook


```yml

---
- name: Drupal Installer Docker
  hosts: drupalserver
  become: true

  vars:
    drupal_project_name: default

    drupal_type_database: mariadb   #mariadb, postgresql
    postgres_version: 14            #12, 13, 14
    mariadb_version: latest         #8.0, 10.0, latest

    drupal_admin_username: admin
    drupal_admin_password: XtremeXxXxX

    drupal_db_name: drupal
    drupal_db_username: admin
    drupal_db_password: XtremeXxXxX

  roles:
    - drupal.docker

```

