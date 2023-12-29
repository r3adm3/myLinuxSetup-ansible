
1. sshkey needs copying up

2. Edit /etc/sudoers
daed    ALL=(ALL) NOPASSWD:  ALL

3. Make sure python pointing to right version on target
```bash
sudo apt install python3 python-is-python3
```

4a. Install all apt packages and cloud tools
```bash
ansible-playbook -i inventory aptpackages.yml -b
```

or 

4b. Install just base OS packages (no cloud tools)
```bash
ansible-playbook -i inventory -b base.yml -u daed -K
```

Troubleshooting across many machines
```bash
ansible linux -a "hostname" -u daed -b -K --inventory-file=./inventory
```