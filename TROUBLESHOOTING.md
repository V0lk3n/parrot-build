# Troubleshooting

## Deprecated Warning

Error :

```bash
ERROR! [DEPRECATED]: ansible.builtin.include has been removed. Use include_tasks or import_tasks instead. This feature was removed from ansible-core in a release after 2023-05-16. Please update your playbooks.
```
Fix :

```
$ grep -HRn ' include:' *
roles/configure-logging/tasks/main.yml:2:- include: "ufw.yml"
roles/configure-logging/tasks/main.yml:3:- include: "auditd.yml"
roles/install-tools/tasks/main.yml:2:- include: apt-stuff.yml
roles/install-tools/tasks/main.yml:3:- include: kerbrute.yml
roles/install-tools/tasks/main.yml:4:- include: github-repos.yml
roles/install-tools/tasks/main.yml:5:- include: python-tools.yml
roles/install-tools/tasks/main.yml:6:- include: gem-tools.yml
roles/configure-system/tasks/main.yml:2:- include: "configure-sudoers.yml"
roles/customize-browser/tasks/main.yml:2:- include: "burp.yml"
roles/customize-browser/tasks/main.yml:3:- include: "firefox.yml"
```

Replace all `include:` to `import-tasks:`

## Failed to find required executable "dconf"

Error :

```bash
TASK [roles/customize-terminal : Read current mate terminal profiles] *****************************************
fatal: [localhost]: FAILED! => {"changed": false, "msg": "Failed to find required executable \"dconf\" in paths: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/games:/usr/games"} 
```

Fix :

```
sudo apt install dconf-cli
```

## Failed to find required executable "ufw"

Error : 

```bash
TASK [roles/configure-logging : Configure UFW] ****************************************************************
fatal: [localhost]: FAILED! => {"changed": false, "msg": "Failed to find required executable \"ufw\" in paths: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"}
```

Fix :

```bash
sudo apt install ufw
```

