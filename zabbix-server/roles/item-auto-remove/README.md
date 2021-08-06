# Auto remoção 
Está role cria o item **Auto remoção** que deleta os hosts que o zabbix não esta mais conseguindo coletar metricas porque a instancia não existe mais na AWS  

## Tarefas  

- Colocara o script **auto-remove.py** no diretorio **/usr/lib/zabbix/externalscripts/** do Zabbix Server  

- Criara o item: **Auto remoção** no host **Zabbix Server**  

## Playbook exemplo

```
---
- hosts: all
  vars:
  # Deixar localhost, colocar /zabbix caso necessite
    ZABBIX_URL: "http://localhost/"
  # Usuario do Zabbix
    ZABBIX_USER: "Admin"
  # Senha do Zabbix
    ZABBIX_PASSWD: "zabbix"
  # access key 
    aws_access_key_id: "coloque_sua_access_key"
  # secret key
    aws_secret_access_key: "coloque_sua_secret_key"
  become: yes

  roles:
    - item-auto-remove
```