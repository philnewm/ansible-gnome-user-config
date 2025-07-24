# Firefox

Role isn't ready yet, further research is necessary:

* https://gist.github.com/aaronlippold/d1183270274568159d6a7b098441ec4c
* https://braheezy.github.io/posts/automating-firefox-with-ansible/
* https://askubuntu.com/questions/73474/how-to-install-firefox-addon-from-command-line-in-scripts
* https://wiki.mozilla.org/Firefox/CommandLineOptions#Using_command_line_options
* https://linuxconfig.org/how-to-customize-firefox-using-the-policies-json-file
* https://gitlab.com/fedora/sigs/flatpak/fedora-flatpaks/-/issues/13

```bash
jq '.addons[] | select(.active == true) | .defaultLocale.name' ~/.mozilla/firefox/nlrguhh6.default_profile_by_ansible/extensions.json
```

[![Alma9-CI](https://github.com/philnewm/ansible-firefox/actions/workflows/alma9-ci-caller.yml/badge.svg)](https://github.com/philnewm/ansible-firefox/actions/workflows/alma9-ci-caller.yml)  [![Rocky9-CI](https://github.com/philnewm/ansible-firefox/actions/workflows/rocky9-ci-caller.yml/badge.svg)](https://github.com/philnewm/ansible-firefox/actions/workflows/rocky9-ci-caller.yml)  [![CentOSStream9-CI](https://github.com/philnewm/ansible-firefox/actions/workflows/centosstream9-ci-caller.yml/badge.svg)](https://github.com/philnewm/ansible-firefox/actions/workflows/centosstream9-ci-caller.yml)  [![Debian12-CI](https://github.com/philnewm/ansible-firefox/actions/workflows/debian12-ci-caller.yml/badge.svg)](https://github.com/philnewm/ansible-firefox/actions/workflows/debian12-ci-caller.yml)  [![Ubuntu2204-CI](https://github.com/philnewm/ansible-firefox/actions/workflows/ubuntu2204-ci-caller.yml/badge.svg)](https://github.com/philnewm/ansible-firefox/actions/workflows/ubuntu2204-ci-caller.yml)

Role description

This role includes a full vagrant based molecule testing setup at `molecule/default`

## Structure

```code
📦 ansible-firefox
 ┣ 📂 defaults
 ┃ ┗ 📜 main.yml
 ┣ 📂 files
 ┃ ┗ 📜 file_placeholder.yml
 ┣ 📂 handlers
 ┃ ┗ 📜 main.yml
 ┣ 📂 meta
 ┃ ┗ 📜 main.yml
 ┣ 📂 molecule
 ┃ ┗ 📂 default
 ┃   ┗ 📜, 📜, 📜, scenario_files
 ┣ 📂 tasks
 ┃ ┣ 📜 main.yml
 ┃ ┣ 📜 present.yml
 ┃ ┣ 📜 dependencies.yml
 ┃ ┣ 📜 absent.yml
 ┃ ┗ 📜 init.yml
 ┣ 📂 templates
 ┃ ┗ ⛩️ template.j2
 ┣ 📂 vars
 ┃ ┗ 📜 main.yml
 ┗ 🗒️ README.md
 ┗ 📓 requirements.txt

```

Describe and explain role structure. 

## Requirements

Elaborate external dependencies and how to use them.

## Role Variables

* defaults/main.yml
  * first_var
  * sec_var
  * third_var
* vars/main.yml
  * first_var
  * sec_var
  * third_var

## Dependencies

List role ansible-galaxy dependencies - if any.

## Example Playbook

Add an example playbook

```yaml
---

tasks:
  - name: Include ansible-firefox present
    ansible.builtin.include_role:
      name: ansible-firefox
    vars:
      state: present
      firefox_source: distro_repo
      firefox_extensions: true
      gnome_favorite: true
...
```

## License

Add license - if any.

## Changes to role template

* Add github action that flags empty directories on release creation

## Git submodule molecule

`git submodule add <url-of-shared-molecule-repo> molecule`

`.git/info/attributes`

```code
molecule/default/cleanup.yml merge=ours
molecule/default/converge.yml merge=ours
molecule/default/verify.yml merge=ours
```

```bash
git submodule update --remote --merge
```

```bash
cd molecule
git pull origin main
```

