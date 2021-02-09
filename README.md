Ansible Playbook to Setup Postgres and Bucardo on Debian OS:

**Bucardo** is an asynchronous [PostgreSQL](https://www.postgresql.org/) replication system, allowing for both multi-master and multi-slave operations. 

This playbook can be used to configure Postgres and Bucardo and create a sync between 2 DBs. 

```
bucardo.yml - Playbook to run
vars.yml - Includes all the values of variable defined in bucardo.yml
confidential.yml - Encrypted yaml file which consists of passwords
Bucardo.pm - Modified file which is used to avoid usage of replication role on destination DB
vault-pass.yml - It has password used to encrypt/decrypt confidential.yml file
```


To run the playbook, please edit vars.yml and confidential.yml and change it with your values.
```
  ansible-playbook --vault-password-file vault-pass.yml bucardo.yml
```
```
Note:- change hosts according to your inventory
```

To view/edit confidential.yml

```
ansible-vault edit confidential.yml

ansible-vault view confidential.yml
```





