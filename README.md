# MattermostPostgresql
## Création des machines vagrant 
```
Créer les 2 machines virtuelles.

Vagrant up
 
Partager le clés ssh 

ssh-copy-id -i ~/.ssh/id_rsa.pub vagrant@192.168.60.21
ssh-copy-id -i ~/.ssh/id_rsa.pub vagrant@192.168.60.20

```
## exemple de plyabook
```
---
- name: configurer mattermost et postgresql
  hosts: mattermost
  vars:
    mattermostip: 192.168.60.21
    ippostgres: 192.168.60.20
    dbname: mattermost
    dbuser: mattermost-user
    dbpassword: password

  become : yes
  roles:
    #- postgresql
- mattermost
```

## Variables
```
    mattermostip: "adresse ip de la machine mattermost"
    ippostgres: "adresse ip de la machine postgresql"
    dbname: nom de la base de donnée(mattermost)
    dbuser: nom de l'utilistateur de la base de donnée
    dbpassword: mot de passe de l'utilisateur
```
## Jouer les playbook
```
ansible-playbook -i inventory ansible-playbook.yml
```

