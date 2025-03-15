---
aliases: 
tags:
  - daily-note
  - nvim
  - terminal
  - workspace
  - environment
created: 2025-03-04T21:41
updated: 2025-03-06T15:32
---

# 2025-03-06 - Daily Note

**Created:** 2025-03-06 15:22
**Author:** GleamTOto

## Summary
<!-- Briefly summarize your learning journey today -->

## Today I Learned
<!-- List out concepts you learned today -->
- Ansible es una ==herramienta de automatización de TI de código abierto que permite configurar sistemas, implementar software, y orquestar flujos de trabajo==. Se puede usar para gestionar la configuración de servidores, dispositivos de red, y proveedores en la nube.

## Archivo neovim.yml
```yml
- name: Build and Install Neovim on macOS
  hosts: localhost
  tasks:
    - name: Install dependencies with Homebrew
      homebrew:
        name:
          - ninja
          - cmake
          - gettext
          - lua
          - luajit
          - unzip
          - curl
          - git
        state: present

    - name: Clone Neovim repository
      ansible.builtin.git:
        repo: "https://github.com/neovim/neovim.git"
        dest: "{{ lookup('ansible.builtin.env', 'HOME')}}/personal/neovim"
        single_branch: yes
        version: v0.10.4

    - name: Ensure build directory is clean
      ansible.builtin.shell:
        cmd: |
          cd {{ lookup('ansible.builtin.env', 'HOME') }}/personal/neovim
          rm -rf build CMakeCache.txt CMakeFiles .deps

    - name: Run CMake with Ninja
      ansible.builtin.shell:
        cmd: |
          cd {{ lookup('ansible.builtin.env', 'HOME') }}/personal/neovim
          cmake -S . -B build -G Ninja

    - name: Build Neovim
      ansible.builtin.shell:
        cmd: |
          cd {{ lookup('ansible.builtin.env', 'HOME') }}/personal/neovim
          make CMAKE_BUILD_TYPE=RelWithDebInfo

    - name: Install Neovim locally (no sudo)
      ansible.builtin.shell:
        cmd: |
          cd {{lookup('ansible.builtin.env','HOME')}}/personal/neovim/build
          cmake .. -DCMAKE_INSTALL_PREFIX {{lookup('ansible.builtin.env','HOME') }}/.local
          ninja install
```

# Commands
# borrar chaché de instalación

```bash
	cd ~/personal/neovim
	rm -rf build CMakeCache.txt CMakeFiles .deps cmake -S . -B build -G Ninja 
	make CMAKE_BUILD_TYPE=RelWithDebInfo
```

# Ejecutar playbook Ansible 

```bash
ansible-playbook -K neovim.yml
```


## Questions

<!-- Questions that arose during your learning -->
- 
## Insights

<!-- Any insights or "aha moments" -->
- 

## Action Items

- [ ]  Task 1
- [ ]  Task 2
- [ ]  Task 3

## Resources

<!-- Resources you found today -->

- [Resource Name](https://github.com/copilot/c/URL)

## Mood

<!-- How are you feeling about your learning? -->
- 

## Tomorrow's Focus

<!-- What will you focus on tomorrow? -->
- 
## Metadata

- Status: #status/active
- Topics: #nvim #daily-learning #environment #workspace 