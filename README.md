# Ansible Postgresql role

[![Lint Ansible roles](https://github.com/francomile/ansible-role-postgresql/actions/workflows/ansible_lint.yml/badge.svg)](https://github.com/francomile/ansible-role-postgresql/actions/workflows/ansible_lint.yml)

[![Release role to Ansible Galaxy](https://github.com/francomile/ansible-role-postgresql/actions/workflows/push_to_galaxy.yml/badge.svg)](https://github.com/francomile/ansible-role-postgresql/actions/workflows/push_to_galaxy.yml)

## Actions of the Role

* Install Postgresql database (Docker)

## Common Usage

```yaml
roles:
  - {
    role: francomile.postgresql,
    postgresql_base_dir: "{{ postgresql_base_dir | default('/opt/postgresql', true) }}",
    postgresql_container_name: "{{ postgresql_container_name | default('postgres'), true }}",
    postgresql_docker_cpu: 2,
    postgresql_docker_image: "postgres:12",
    postgresql_docker_memory: "4GB",
    postgresql_docker_network: "traefik",
    postgresql_db_name: "postgresdb",
    postgresql_db_user: "postgresuser",
    postgresql_db_password: "myPassword",
    postgresql_expose_port: 5432,
    postgresql_autovacuum_work_mem: "128MB",
    postgresql_log_line_prefix: "%m [%p] %q%u@%d(%h) ",
    postgresql_log_min_error_statement: "warning",
    postgresql_log_statement: "ddl",
    postgresql_maintenance_work_mem: "256MB",
    postgresql_shared_buffers: "512MB",
    postgresql_work_mem: "8MB",
    tags: ["postgres"]
  }
```

## Run the playbook

```shell
ansible-playbook -i inventory playbook.yaml -t "postgres"
```
