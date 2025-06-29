# Começando no Ansible: Conceitos e Projectos

## Instalando o Ansible

Primeiro clone o repositório:

```bash
git clone https://github.com/Mateus-Sebastiao/automation-with-ansible.git
cd automation-with-ansible
```

Depois, garanta que o `pip` está disponível. Digite o comando: 

```bash
$ python3 -m pip -V
```

Se tudo estiver bem, você deverá ver algo como o seguinte:

```bash
$ python3 -m pip -V
pip 22.0.2 from /usr/lib/python3/dist-packages/pip (python 3.10)
```

Então avancemos para próxima etapa.

Você pode instalar o Ansible directamente no teu usuário local com o comando:

```bash
$ python3 -m pip install --user ansible
```

Ou podes usar um ambiente virtual para isso, como eu fiz. Crie um diretório, como: `automation-with-ansible`; digite o seguinte dentro do mesmo:

```bash
$ python3 -m venv venv
$ source venv/bin/activate
(venv) $ pip install ansible
(venv) $ ansible-community --version
```

Se tudo estiver bem, a saída deve ser algo como o seguinte:

```bash
(venv) $ ansible-community --version
Ansible community version 10.7.0
```

## Criando Ambiente de Teste

### Opção A – Usando Docker

Se não tens máquinas remotas e quer testar localmente, pode criar um container com SSH e usá-lo como host remoto.

Eu usei container para isso. Criei um ficheiro `Dockerfile.ssh-server` para criar containers com SSH. Para rodar containers e praticar; mas fiz questão de subir a imagem no [meu repositório no Docker Hub](https://hub.docker.com/r/mateussebastiao/custom-ssh-server) para facilitar a sua vida, você só tem que digitar o seguinte:

```bash
$ docker pull mateussebastiao/custom-ssh-server:latest
```

1. Para rodar o container, digite:

```bash
$ docker run -d --name ssh-host1 --hostname ssh-host1 -p 2222:22 mateussebastiao/custom-ssh-server
```

2. Teste a conexão via senha:

```bash
$ ssh mateus@172.17.0.2
# Senha: mateus
# IP: Com base no teu endereço
```

3. Gerar par de chaves (caso não tenha)

No seu host Linux:

```bash
$ ssh-keygen -t rsa -b 2048 -f ~/.ssh/ansible_key
```
> Quando pedir uma passphrase, você pode deixar em branco por agora.

Esse comando cria dois arquivos:
    `~/.ssh/ansible_key` → chave privada (você guarda com segurança)
    `~/.ssh/ansible_key.pub` → chave pública (você envia para o servidor)


4. Rode o `ssh-copy-id`:

```bash
$ ssh-copy-id -i ~/.ssh/ansible_key.pub mateus@172.17.0.2
```

5. Teste a conexão usando par de chaves:

```bash
$ ssh mateus@172.17.0.2
```

Quer dizer, que você pode rodar quantos containers desejar e praticar o Gerenciamento de Infraestrutura com Ansible. Vamos lá!!!

### Opção B – Já tem VMs?

Se já tens uma VM com IP e SSH (por exemplo, `192.168.56.10` com login `mateus`), já podes testá-la direto.

## Inventários, Playbooks,...

Caso tudo esteja funcionando, você pode se divertir aprendendo sobre conceitos nos projectos anexados. Vamos lá!

- [Construindo um inventário e criando um playbook - 01](./01-building-an-inventory/)
- [Automatizando a instalação do Nginx num Servidor Remoto](./02-automate-nginx-installation/)

***
Desenvolvido por: **Mateus Sebastião**