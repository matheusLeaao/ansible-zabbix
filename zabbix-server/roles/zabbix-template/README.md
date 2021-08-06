Requerimentos
-------------

Tarefas
-------

Será importado todos os templates no formato XML que estão dentro do diretorio "templates". 
Atualmente, esta o "Template OS Linux - Mandic" e "Template OS Windows - Mandic".

Caso queira colocar um novo template colocar no formado "zabbix_*<nome_do_template>*.xml" dentro do diretorio "templates" encontrado na role.

Playbook Exemplo
----------------

    - hosts: All
      
      vars:
        ####Colocar URL do Zabbix API executada de dentro do host
        url_zabbix_api: "http://localhost/api_jsonrpc.php"
        
        ####Usuário e senha do Zabbix Server
        user_zabbix: Admin
        pass_zabbix: zabbix

      roles:
        - zabbix-templates