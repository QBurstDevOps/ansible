ansible
=======

Ansible Playbooks for Server orchestration

To install from source.

Method 1
========

$ git clone git://github.com/ansible/ansible.git --recursive
$ cd ./ansible
$ source ./hacking/env-setup

Method 2
========

Checkout this repository where you can find the ansible-source directory with the actual source at the time of writing this doc.
$ git clone https://github.com/QBurstDevOps/ansible.git
$ cd ./ansible-source
$ source ./hacking/env-setup

If you don’t have pip installed in your version of Python, install pip:

$ sudo easy_install pip

Ansible also uses the following Python modules that need to be installed:

$ sudo pip install paramiko PyYAML jinja2 httplib2

Note when updating ansible, be sure to not only update the source tree, but also the “submodules” in git which point at Ansible’s own modules (not the same kind of modules, alas).

$ git pull --rebase
$ git submodule update --init --recursive

Once running the env-setup script you’ll be running from checkout and the default inventory file will be /etc/ansible/hosts. You can optionally specify an inventory file (see Inventory) other than /etc/ansible/hosts:

$ echo "127.0.0.1" > ~/ansible_hosts
$ export ANSIBLE_HOSTS=~/ansible_hosts

You can read more about the inventory file in later parts of the manual.

Now let’s test things with a ping command:

$ ansible all -m ping --ask-pass


