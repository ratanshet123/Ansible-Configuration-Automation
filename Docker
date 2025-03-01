FROM ubuntu:22.04

# Install Ansible and dependencies
RUN apt-get update && apt-get install -y ansible git

# Set working directory
WORKDIR /ansible

# Copy your playbooks and inventory
COPY . .

# Run Ansible
CMD ["ansible-playbook", "-i", "inventory/production", "playbooks/site.yml"]
