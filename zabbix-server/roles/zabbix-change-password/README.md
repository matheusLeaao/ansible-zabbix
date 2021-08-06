# Instancias não monitoradas  
Está role cria o item **Instancias não monitoradas** que retorna o IP das instancias na AWS que não estão sendo monitoradas  

## Tarefas  

- Colocara o script **item-instances-no-monit.py** no diretorio **/usr/lib/zabbix/externalscripts/** do Zabbix Server  

- Criara o item: **Instancias não monitoradas** no host **Zabbix Server**  

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
  # IP privado do Zabbix
    ZABBIX_PRIVATE_IP: "172.31.89.109"
  # access key 
    aws_access_key_id: "coloque_sua_access_key"
  # secret key
    aws_secret_access_key: "coloque_sua_secret_key"
  become: yes

  roles:
    - item-instancias-nao-monitoradas
```