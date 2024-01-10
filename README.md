# Ansible Role: semaphore.docker

A full list of defaults and their values can be found in the `defaults/main.yml`.

Author : Alexander Aguilar
email  : alexolomeo@gmail.com

## host file

[semaphoreui]
localhost

[semaphoreui:vars]
ansible_user=ubuntu
#ansible_become=yes
#ansible_become_method=sudo
ansible_port= 2244
ansible_ssh_private_key_file= ./KEY-UBUNTU


## Example Playbook


```yml

---
- name: semaphore
  hosts: semaphoreui
  become: true

  vars:
    semaphore_type_database: mysql
    semaphore_admin_username: admin
    semaphore_admin_password: XtremeXxXxX

    semaphore_db_name: semaphore
    semaphore_db_username: semaphore
    semaphore_db_password: semaphore


  roles:
    - semaphore.docker

```

