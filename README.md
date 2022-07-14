# mngm-ubuntu
Ansible Playbooks para gerenciamento de servidores Ubuntu

### Template/Playbook para criação de usuário
comando para gerar criptografia de senha para adicionar usuário, a saída desse comando é o #hash que deve ser adicionado a variável **PasswordNewUser** no template/playbook de adição de usuários
```
mkpasswd --method=sha-512 PASSWORD
```
variáveis do template
```
NewUser: <USERNAME>
PasswordNewUser: <SAIDA: mkpasswd --method=sha-512 PASSWORD>
CommentNewUser: '<Comentario USUARIO>'
```

### Template/Playbook para controle de acesso via SSH
variáveis do template
```
allowed_users: <USER1> <USER2> <USERn>
allowed_groups: None
deny_users: None
deny_groups: None
```
- **lista** com espaço entre os usuário
- **None**, não verifica opção (skip)


### Template/Playbook de atualização do sistema (apt upgrade)
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
