# Install Docker and Tenable Nessus using Ansible

This Ansible playbook automates the installation of Docker and Tenable Nessus on a Red Hat 8 operating system.

## Prerequisites

- Ansible 2.10 or later installed on the control machine
- Red Hat 8 operating system installed on the target machine
- Internet connection on the target machine

## Usage

1. Clone this repository to your local machine: `git clone https://github.com/example/install-docker-nessus.git`
2. Update the `vars/nessus.yml` file with a secure password for the Nessus administrator account.
3. Run the playbook using the following command: `ansible-playbook -i inventory.yml playbook.yml --tags "common,docker,nessus"`
   - This command will install Docker and Tenable Nessus and start the Nessus container with port 8834 exposed.
   - You can also run individual roles or tags by specifying them in the `--tags` option. For example, to only install Docker, you can run: `ansible-playbook -i inventory.yml playbook.yml --tags "common,docker"`
4. Access the Nessus web interface by navigating to `https://<target_ip>:8834` in a web browser and logging in with the Nessus administrator credentials.

## Directory Structure

install-docker-nessus/
├── inventory.yml
├── playbook.yml
├── roles
│ ├── common
│ │ └── tasks
│ │ └── main.yml
│ ├── docker
│ │ └── tasks
│ │ └── main.yml
│ └── nessus
│ └── tasks
│ └── main.yml
└── vars
└── nessus.yml


## Variables

- `nessus_admin_password`: The password for the Nessus administrator account. This variable is defined in `vars/nessus.yml` and should be updated to a secure value.

## License

This playbook is licensed under the MIT License. See the LICENSE file for details.

