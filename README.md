ansible
=======

Ansible Playbooks for Server orchestration

To install from source.
<pre>
$ git clone git://github.com/ansible/ansible.git --recursive
$ cd ./ansible
$ source ./hacking/env-setup
</pre>

If you don’t have pip installed in your version of Python, install pip:
<pre>
$ sudo easy_install pip
</pre>

Ansible also uses the following Python modules that need to be installed:
<pre>
$ sudo pip install paramiko PyYAML jinja2 httplib2
</pre>

Note when updating ansible, be sure to not only update the source tree, but also the “submodules” in git which point at Ansible’s own modules (not the same kind of modules, alas).
<pre>
$ git pull --rebase
$ git submodule update --init --recursive
</pre>

Once running the env-setup script you’ll be running from checkout and the default inventory file will be /etc/ansible/hosts. You can optionally specify an inventory file (see Inventory) other than /etc/ansible/hosts:
<pre>
$ echo "127.0.0.1" > ~/ansible_hosts
$ export ANSIBLE_HOSTS=~/ansible_hosts
</pre>


You can read more about the inventory file in later parts of the manual.

Now let’s test things with a ping command:
<pre>
$ ansible all -m ping --ask-pass
</pre>

