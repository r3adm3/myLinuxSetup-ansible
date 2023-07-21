
sshkey needs copying up

/etc/sudoers
daed    ALL=(ALL) NOPASSWD:  ALL

ansible-playbook -i inventory aptpackages.yml -b
ansible-playbook -i inventory -b base.yml -u daed -K
sudo apt install python3 python-is-python3
ansible linux -a "hostname" -u daed -b -K --inventory-file=./inventory