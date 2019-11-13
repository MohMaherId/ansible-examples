# Important Note
Before running ansible playbooks, make sure to add your ansible controller public key to the remote server nodes
under remote_user/.ssh/authorized_keys

```bash
# Generate your key (default folder under ~/.ssh/ )
ssh-keygen -t rsa -b 4096 -C "my.email@email.com"
```

```bash
# Exchange the ssh authorized keys to remote server (e.g. AWS)
cat ~/.ssh/id_rsa.pub | ssh ec2-user@ec2-xx-xx-xx-xx.compute-1.amazonaws.com 'mkdir -p .ssh; cat >> .ssh/authorized_keys'

# [or simply use:]

ssh-copy-id ec2-user@ec2-xx-xx-xx-xx.compute-1.amazonaws.com
```

For accessing AWS you may need your PEM file. Also in your inventory host file you may need to set vars: ansible_ssh_private_key_file to reference the pem file.