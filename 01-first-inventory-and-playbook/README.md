# Construindo um Inventário - Conceito 01

O `inventory` é um dos conceitos do Ansible, antes de você testar esse projecto simples, deves saber o conceito por trás dele. Se cumpriste com essa etapa, vamos lá.

## Pré-requisitos

- Rodar containers ou ter provisionado VMs; podes seguir as minhas diretrizes no [README.md](../README.md) principal do repositório sobre como rodar containers com Docker, explico lá;
- Ansible instalado, kkk.

## Testando o `inventory.ini` ou `inventory.yml`

Se tiveres tudo a funcionar com base nos pré-requisitos, que explico no [README.md](../README.md). Avance fazendo:

```bash
(venv) $ cd 01-building-an-inventory/
```

Verifique o inventário:

```bash
(venv) $ ansible-inventory -i inventory.ini --list
```

<div align="center">
    <img src="./media/step-01.png" alt="Listando o inventário">
</div>

Testar ping:

```bash
(venv) $ ansible ssh -m ping -i inventory.ini
```

<div align="center">
    <img src="./media/step-02.png" alt="Ping">
</div>