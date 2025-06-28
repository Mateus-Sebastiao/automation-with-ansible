# Começando no Ansible: Conceitos e Projectos

## Instalando o Ansible

Garanta que o `pip` está disponível. Digite o comando: 

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
$ ansible-community --version
Ansible community version 10.7.0
```

## Criando Ambiente de Teste

### Opção A – Usando Docker

Se não tens máquinas remotas e quer testar localmente, pode criar um container com SSH e usá-lo como host remoto.

Eu usei container para isso, mas caso já tenhas VMs, vá para opção B se achares melhor.

### Opção B – Já tem VMs?

Se já tens uma VM com IP e SSH (por exemplo, `192.168.56.10` com login `mateus`), já podes testá-la direto.

## Inventários, Playbooks,...

Caso tudo esteja funcionando, você pode se divertir aprendendo sobre conceitos nos projectos anexados. Vamos lá!

***
Desenvolvido por: **Mateus Sebastião**