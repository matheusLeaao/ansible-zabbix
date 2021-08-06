# pagerduty

Requerimentos
-------------

Necessário "jq" no host onde esta o Ansible

*Ubuntu*

`apt install jq -y`

*Centos*

`yum install jq -y`

Tarefas
-------

Será executado a instalação do PagerDuty agent e via API do Zabbix, será criado um MediaType, um UserGroup, um User e uma Action.

Os nomes dos itens criados será:

MediaType: PagerDuty
UserGroup: Integrations
User: PagerDuty (Variavel "pd_name")
Action: PagerDuty (Variavel "pd_name

Playbook Exemplo
----------------

    - hosts: All
      become: true
      
      vars:
        ####Colocar token da integração criada dentro do serviço no PagerDuty
        token_pagerduty: "COLOCARTOKENAQUI"
        
        ####Nome que será no User e Action dentro do Zabbix
        pd_name: "Mandic"
        
        ####Colocar URL do Zabbix API executada de dentro do host
        url_zabbix_api: "http://localhost/api_jsonrpc.php"
        
        ####Usuário e senha do Zabbix Server
        user_zabbix: Admin
        pass_zabbix: zabbix

      roles:
        - pagerduty