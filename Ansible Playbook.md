# Ansible Playbook:

**Definition:**
An Ansible playbook is a script written in YAML (Yet Another Markup Language) that defines a set of tasks, configurations, and roles to be executed on remote hosts. Playbooks are a fundamental concept in Ansible and serve as the primary means of automation.

**Key Components:**

- **Hosts:**
        Playbooks target specific hosts or groups of hosts defined in the Ansible inventory. The inventory specifies where the tasks in the playbook should be executed.

- **Tasks:**
        A task is a single unit of work in an Ansible playbook. Tasks are defined to perform specific actions, such as installing packages, copying files, or restarting services. Each task is associated with a module that encapsulates the logic for that action.

- **Modules:**
        Modules are reusable, standalone scripts that Ansible uses to perform specific operations on managed nodes. They abstract the underlying system details and provide a consistent interface. Tasks invoke modules to achieve the desired state on the managed nodes.

- **Roles:**
        Roles are a way to organize and structure playbooks. They allow you to group related tasks, variables, and files together, promoting modularity and reusability. Roles help manage complex automation scenarios more effectively.

- **Variables:**
        Playbooks can use variables to store data that may change based on the target host or the desired configuration. Variables make playbooks more flexible and dynamic.


```yaml
- name: Example Playbook
  hosts: web_servers
  become: yes  # Run tasks with elevated privileges

  tasks:
    - name: Ensure Apache is installed
      apt:
        name: apache2
        state: present

    - name: Copy configuration file
      copy:
        src: /path/to/apache.conf
        dest: /etc/apache2/apache.conf
      notify:
        - Restart Apache

  handlers:
    - name: Restart Apache
      service:
        name: apache2
        state: restarted

```

### Explanation:

> This playbook targets hosts in the "web_servers" group. It contains two tasks: one to ensure Apache is installed, and another to copy a configuration file. The handlers section defines a handler to restart Apache when notified. The playbook is written in YAML for readability and simplicity.

