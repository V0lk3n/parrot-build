** Make sure to pip install ansible, apt has an older copy **

# Porting to kali
* Fix ansible-playbook deprecation warnings
* Change Firefox Home page from parrot to local kali home page
* Add Troubleshooting guid

# Instructions
* Install Ansible 

`python3 -m pip install ansible`

* Clone and enter the repo

`git clone https://github.com/v0lk3n/parrot-build.git && cd parrot-build`

* Install ansible-galaxy requirements

`ansible-galaxy install -r requirements.yml`

* Make sure we have a sudo token

`sudo whoami`

* Install dconf-cli and ufw 

`sudo apt install dconf-cli ufw`

* Install ansible playbooks

`ansible-playbook main.yml`

# Off-Video Changes
* Mate-Terminal Colors, I show how to configure it here (https://www.youtube.com/watch?v=2y68gluYTcc). I just did the steps in that video on my old VM to backup the color scheme, then copied it to this repo.
* Evil-Winrm/Certipy/SharpCollection/CME/Impacket, will make a video for these soon
* Updated BurpSuite Activation. Later versions of ansible would hang if a shell script started a process that didn't die. Put a timeout on the java process

# Troubleshooting guide

Refere to <a href="TROUBLESHOOTING.md">TROUBLESHOOTING.md</a>

# Play Recap

```bash
PLAY RECAP ****************************************************************************************************
localhost                  : ok=46   changed=24   unreachable=0    failed=0    skipped=10   rescued=0    ignored=0
```

# To do 
* Port the terminal change
* Something i forgot?
