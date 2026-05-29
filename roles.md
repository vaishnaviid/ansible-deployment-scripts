# ansible roles 
Ansible roles are a way to organize and reuse Ansible code. They allow you to break down your playbooks into smaller, more manageable pieces, making it easier to maintain and share your code.

A role is a collection of tasks, handlers, variables, files, templates, and other resources that are organized in a specific directory structure. Each role has a specific purpose and can be reused across multiple playbooks.
The directory structure of a role typically looks like this:

``` bash
my_role/
├── tasks/
│   └── main.yml
├── handlers/
│   └── main.yml
├── vars/
│   └── main.yml
├── files/
│   └── some_file.txt
├── templates/
│   └── some_template.j2
└── meta/
    └── main.yml
```
- `tasks/`: Contains the main tasks of the role, defined in `main.yml`.
- `handlers/`: Contains handlers that can be triggered by tasks, defined in `main.yml`.
- `vars/`: Contains variables that can be used in the role, defined in `main.yml`.
- `files/`: Contains static files that can be copied to the target hosts.
- `templates/`: Contains Jinja2 templates that can be rendered and copied to the target hosts.
- `meta/`: Contains metadata about the role, such as dependencies on other roles.
- `default/`: contains default values
To use a role in a playbook, you can include it using the `roles` keyword. For example:

``` yaml
- hosts: targetserver
  roles:
    - my_role
```