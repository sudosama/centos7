# Centos 7 - Lampp
Guida rapida all'installazione dei principali servizi per la messa in opera di un sistema di hosting di base:
- Http(+ php)
- MYsql( + phpmyadmin)
- FTP

## Informazione sistema:
![Os](img/os.PNG)

## Informazione rete:
![rete](img/network.PNG)

## Installazione servizi ssh: 
I comandi per installare il servizio ssh su Centos7
```
  yum install sshd
  systemctl start sshd
  systemctl enable sshd
  
```

Status SSH
![phpmyadmin](img/statusSSH.PNG)

## Privileggi ssh:
Configurare con un editor(vim) sul file di configurazione per modificare i comportamenti di default, togliendo hashtag davanti
```
 Port //change port default
 
 PermitRootLogin no
 AllowUsers ebeta
```
![SSH](img/configSSH.PNG)

## HTTP

installazione e avvio del servizio http

```
  yum install httpd
  systemctl start httpd
  systemctl enable httpd
```
Controllo lo stato del servizio
![statusphpmyadmin](img/statusHTTP.PNG)


Configurare il firewall per permettere l'accesso alla porta di default di HTTP(80/tcp) e caricamento delle impostazioni
```
  firewall-cmd --permanent --add-port=80/tcp
  firewall-cmd --reload
  
```

Testing il servizio via web

![testingWeb](img/checkHTTP.PNG)


## Installazione il servizion di Mysql
Comando per scaricare RPM
```
sudo rpm -ivh mysql57-community-release-el7-9.noarch.rpm
```


installazione mysql server
```
sudo yum install mysql-server

```

l'avvio e status del servizio mysql

```
 sudo systemctl start mysqld
 sudo systemctl status mysqld
  
```

![OS](img/statusMySQL.PNG)

Versione mysql

![OS](img/versionMySQL.PNG)


## installazione servizio phpmyadmin

```
  sudo yum -y install phpmyadmin
  
```

![configPhpmyadmin](img/configPhpMyAdmin.PNG)
