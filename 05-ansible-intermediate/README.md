# Ansible: Nível Intermediário

Cheguei até aqui, já me sinto um usuário intermediário, sério, kkk! Já se nota pelos diretórios e a quantidade de ficheiros que aqui se tem; diretórios de inventários, ficheiros de configurações padrões, váriaveis de grupo, playbook,...

Mas vamos ao que interesssa... para rodar esse playbook `webservers.yml`, você só tem que fazer:

```bash
(venv) $ ansible-playbook webservers.yml
```

PS: Lembrar que no container você tem que rodar:

```bash
$ docker run -d --name ssh-host2 --hostname ssh-host2 -p 2222:22 -p 8080:8080 mateussebastiao/custom-ssh-server
```

Sem esquecer de copiar a chave ssh para o container.