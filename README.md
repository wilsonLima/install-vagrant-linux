install-vagrant-linux
=========

Role do Ansible com os passos para a instalação do Vagrant em distribuições Linux.

Distribuições Suportadas pela Role
------------

- Fedora 28 ou superior
- Linux Mint LMDE 3 (64 bits) ou superior
- Linux Mint 19.2 (64 bits) ou superior
- openSUSE Leap 15.0 ou superior
- Ubuntu 19.04 (64 bits) ou superior


Tags da Role 
--------------

- main: Tag a ser utilizada em conjunto com outras tags, se alguma tag for especificada no comando.

- vagrant: Realiza a instalação do Vagrant.


Variáveis da Role 
--------------

- vagrant_version_dir: Versão do Vagrant, valor padrão: 2.3.6 .
- vagrant_version_bin: Versão do Vagrant, valor padrão: 2.3.6-1 .


Dependências da Role 
--------------

Linux Mint e Ubuntu:

- openssh-server. Ex.: sudo apt install openssh-server


Exemplo de Inventario
----------------

Exemplo de arquivo de hosts: pasta_invetario/hosts

    [NOME]
    IP ansible_connection=ssh ansible_ssh_user=USUARIO ansible_ssh_pass=SENHA_URUARIO ansible_become_pass=SENHA_ROOT


Especificar interpretador python 3: pasta_invetario/group_vars/all

    ansible_python_interpreter: "/usr/bin/python3"


Exemplo de Playbook
----------------

Exemplo de uso da Role, com as configurações padrão:

    - hosts: desktop
      roles:
         - install-vagrant-linux

Exemplo de uso da Role com variáveis:

    - hosts: desktop
      roles:
         - { role: install-vagrant-linux, vagrant_version: 2.2.19 }


Exemplo de Comandos
----------------

Comando para executar todas as tasks:

    ansible-playbook -i <caminho_inventario> <caminho_playbook>

Comando para executar a tag "vagrant" (em caso de uso de tags, a tag "main" é obrigatória):

    ansible-playbook -i <caminho_inventario> <caminho_playbook> --tags "main, vagrant"


License
-------

MIT