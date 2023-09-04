# Ubuntu (Debian) development machine setup

This is a Ansible playbook that sets up a Debian development machine with all the necessary configurations and software packages.

### What does it do?

1. Install all the specified packages in `vars/main.yaml` unde the `apt_packages` section.
2. Install Docker.
3. Sets up the dotfiles (using geerlingguy.dotfiles role) if `configure_dotfiles` is set to true.

### How to use it?

1. Install the `geerlingguy.dotfiles` role local to this playbook

```sh
ansible-galaxy install geerlingguy.dotfiles -p roles/
```

2. Modify the default parameters from `vars/main.yaml` file
   -  Add packages to the `apt_packages` section
   -  Change the username to the machine specific one (changes would be required if multiple machines are targeted)
   -  choose if you want to install dotfiles by changing `configure_dotfiles` to true or false, then select the dotfiles repo and dotfiles files.
  
3. Add the machine `ip`, `ansible_user` and `ansible_ssh_private_key_file` location to the `template_inventory.ini` file and rename it to `inventory.ini`
4. Run the playbook from the root of the project directory

```sh
ansible-playbook main.yaml -i inventory.ini -K
```


### Tools to still install

1. VS Code
2. Sublime Text Editor
3. Wireshark
4. Postman

This project is still work in progress
