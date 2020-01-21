# Ansible playbook: secure-server

The objective of this project is to group in the same playbook, different roles that configure and provision the typical services that make good security practices on Debian-based servers

At the moment, the services included are:
* SSH server
* Fail2ban
* Firewall

And it's increasing...

The project uses [galaxy roles](https://galaxy.ansible.com/), and presents a structure that seeks to facilitate the parameterization in the provisioning of our infrastructure through `host_vars` and `group_vars`, taking a look at the sample variables ;)

# Previous requirements
* [git](https://git-scm.com/downloads) installed.
* [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) installed.

# Getting started

Download the playbook to your PC:
```bash
user@pc:~$ git clone https://github.com/santiagomr/ansible-secure-server.git
```

Enter the root directory of the project, and download the roles from the galaxy using what is specified in the `requirements.yml` file:
```bash
user@pc:~/ansible-secure-server$ ansible-galaxy install -r requirements.yml
```

Once the roles are downloaded, it only remains to prepare your inventory of servers (on which you already have SSH access), host and group variables for your infrastructure according to the examples included. If you still don't flow with Ansible and need some more help, [check the official documentation](https://docs.ansible.com/ansible/latest/user_guide/intro_getting_started.html)

**Finally, you can provision and secure your servers by running the `secure_server.yml` playbook:**

```bash
user@pc:~/ansible-secure-server$ ansible-playbook secure_server.yml
```
