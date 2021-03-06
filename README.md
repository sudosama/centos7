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

![versionmysql](img/versionMySQL.PNG)



## installazione servizio phpmyadmin

```
  yum install php
  systemctl restart httpd
  php -v
  
```
File di configurazione di phpmyadmin

![configPhpmyadmin](img/configPhpMyAdmin.PNG)

Testing servizio phpmyadmin via web

![checkphpmyadmin](img/checkPhpMyAdmin.PNG)


## installazione servizio php

```
  sudo yum -y install phpmyadmin
  
```

Per testare il funzionamento di php creare un file `info.php`, nella ***DocumentRoot***, contenente il codice seguente
```
  <HTML>
    <HEAD></HEAD>
    <BODY>
      <?php phpinfo(); ?>
    </BODY>
  </HTML>
```
![phpinfo](img/infoPHP.PNG)


## installazione servizio ftp

```
  install vsftpd
  
```

Modificare i privileggi nel percorso etc/vsftpd/vsftpd.conf

```
  anonymous_enable=NO
  
```
Abilita l'accesso agli utenti del server locali

```
 local_enable=YES
 
```

Restartare i servizi
```
 systemctl enable vsftpd
 
```
Testing 


![ftp](https://user-images.githubusercontent.com/77326001/112944931-dc480880-9133-11eb-86a8-47c8f1200442.jpeg)











