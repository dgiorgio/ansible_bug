There is a bug in Ansible, which does not load the meta dependencies.
When defining the meta on multiple roles, if the role that runs before is not
loaded, the next role does not execute the meta.
eg: 'role-commons' role is a role dependencies of roles 'role1' and 'role2',
if the var condition 'run_role1' is false, when executing the role 'run_role2',
the meta (dependencies) calling role 'role-commons' is not loaded.

run the playbook
```
ansible-playbook ./playbook.yml
```
