This folder can override ansible defaults by mapping it to /etc/volumes. 

```yaml
...
volumes:
    # map local folders to image volumes
    - ./ansible-etc:/etc/ansible
```

These files will override the ansible files:
* hosts -> /etc/ansible/hosts
* ansible.cfg -> /etc/ansible/ansible.cfg