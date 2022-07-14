# mngm-ubuntu
Ansible Playbooks para gerenciamento de servidores Ubuntu

### Template/Playbook para criação de usuário  
comando para gerar criptografia de senha para adicionar usuário, a saída desse comando é o #hash que deve ser adicionado a variável **PasswordNewUser** no template/playbook de adição de usuários
```
mkpasswd --method=sha-512 PASSWORD
```


### Template/Playbook de atualização do systema (apt upgrade)
variável to template
```
update_mode: safe
```
- If yes or safe, performs an aptitude safe-upgrade.
- If full, performs an aptitude full-upgrade.
- If dist, performs an apt-get dist-upgrade.

Choices:
- dist
- full
- no ← (default)
- safe
- yes
