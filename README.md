# Ansible project creation script

This project is made by Marco Sepp to automate Ansible project creation.

Script will create Ansible project, initalize new local Git repository and create Python virual environment for Ansible installation.

# Requirements

* Linux distro in development computer
* Python3
* Pip3
* Access to Pypi.org or any local Pypi server

# Project structure

The script will create following directory structure with example files. The directory structure is a best practice for Ansible project: https://docs.ansible.com/ansible/2.9/user_guide/playbooks_best_practices.html#alternative-directory-layout

All directories contain a `README.md` file that describes the directory purpose.

```sh
<your-project-name>/                    #  Project root directory
    inventories/                        #  Project inventories directory
        production/                     
            group_vars/
                all.yml                 #  here we assign variables to particular groups
                README.md
            host_vars/
                hostname.yml            #  here we assign variables to particular systems
                README.md
            hosts                       #  Inventory file for production servers
            README.md
        README.md

    <your-project-name>-venv/           #  Python3 virtual environment

    library/                            #  if any custom modules, put them here (optional)
        README.md
    
    module_utils/                       #  if any custom module_utils to support modules, put them here (optional)
        README.md
    
    playbooks/
        playbook.yml                    #  Master playbook
        README.md

    roles/
        README.md

    .gitignore                          #  Gitignore for the project
    ansible-requirements.yml            #  Ansible requirements for the project
    ansible.cfg                         #  Ansible config file for the project
    python-requirements.txt             #  Python requirements fot the project
    README.md
```

# How to use?

Clone this repository:

```sh
$ git clone https://github.com/marcosepp/ansible-project-create.git
$ cd ansible-project-create
```

Add execution permissions for script:

```sh
$ chmod u+x create-ansible-project
```

Run `create-ansible-project` script. Replace `<your-project-name>` with your project name.

```sh
$ ./create-ansible-project <your-project-name>
```

# Install dependencies

To use Python virtual environement for local testing, install Python requirements.

In the created project directory run:

```sh
$ source ./<your-project-name>-venv/bin/activate
$ pip install -r python-requirements.txt
```

Replace `<your-project-name>` with your project name.

# Licence

MIT

# Credits

Marco Sepp
