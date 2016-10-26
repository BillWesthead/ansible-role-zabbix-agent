# ansible-zabbix-agent
Installs and configure Zabbix agent.

### Dependencies
None.

### Role variables
|Key|Type|Description|Default|
|:--|:---|:----------|:------|
|zabbix_agent_version|String|Install version.|3.2|
|zabbix_agent_server|String|Zabbix server host.|127.0.0.1|
|zabbix_agent_ListenIP|String|List of comma delimited IP addresses that the agent should listen on.|0.0.0.0|
|zabbix_agent_ListenPort|Integer|Listen port number.|10050|
|zabbix_agent_Hostname|String|My hostname.|`ansible_fqdn`|

## Dependencies
None.

## Example playbook
+ [firewalld](https://github.com/shomatan/ansible-firewalld.git)

```yaml
- hosts: all
  roles:
    - { role: firewalld }
    - { role: zabbix-agent }
  vars:
    zabbix_agent_server: 192.168.1.1
  tasks:  
    - firewalld: port={{ zabbix_agent_ListenPort }}/tcp permanent=true state=enabled immediate=true

```
