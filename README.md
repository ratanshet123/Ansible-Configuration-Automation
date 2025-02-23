# Ansible-Configuration-Automation

# Ansible Project Documentation

## Overview
This project automates the configuration of web and database servers across different environments using Ansible. It includes playbooks, roles, and inventory files to deploy and manage services like Apache and MySQL.

## Project Structure
```
d:/Ansible/
|-- inventory/
|   |-- production
|   `-- staging
|-- playbooks/
|   |-- dbserver.yml
|   |-- site.yml
|   |-- test_dbserver.yml
|   |-- test_webserver.yml
|   `-- webserver.yml
|-- roles/
|   |-- dbserver/
|   |   `-- tasks/
|   |       `-- main.yml
|   `-- webserver/
|       `-- tasks/
|           `-- main.yml
`-- vars/
    |-- dbserver_vars.yml
    `-- webserver_vars.yml
```


## Playbooks
- **`site.yml`**: Main playbook to deploy both web and database servers.
- **`webserver.yml`**: Playbook to install and configure Apache.
- **`dbserver.yml`**: Playbook to install and configure MySQL.
- **`test_webserver.yml`**: Playbook to test the `webserver` role.
- **`test_dbserver.yml`**: Playbook to test the `dbserver` role.

## Roles
- **`webserver`**: Role to install and configure Apache.
- **`dbserver`**: Role to install and configure MySQL.

## Inventory
- **`inventory/production`**: Inventory file for production environment.
- **`inventory/staging`**: Inventory file for staging environment.

## Usage
1. **Install Ansible**:
   ```bash
   sudo apt update
   sudo apt install ansible
   ```

2. **Run the Playbooks**:
   - Deploy both web and database servers:
     ```bash
     ansible-playbook -i inventory/production playbooks/site.yml
     ```
   - Test the `webserver` role:
     ```bash
     ansible-playbook playbooks/test_webserver.yml
     ```
   - Test the `dbserver` role:
     ```bash
     ansible-playbook playbooks/test_dbserver.yml
     ```

## Variables
- **`vars/webserver_vars.yml`**: Variables for the `webserver` role.
- **`vars/dbserver_vars.yml`**: Variables for the `dbserver` role.

## Best Practices
- Use tags to run specific tasks or roles.
- Test playbooks in a staging environment before deploying to production.
- Document any changes or updates to the playbooks and roles.

## Future Enhancements
- Add more roles for additional services.
- Integrate with CI/CD pipelines for automated deployments.
- Expand inventory files for different environments.

