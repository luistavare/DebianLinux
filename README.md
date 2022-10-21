# DebianLinux
## basicos

atualizar os pacotes:
```
$ sudo apt update
$ sudo apt upgrade
```
As vezes vai pedir para reiniciar 
```
$ sudo reboot
```

mudar o hostname (para atualizar o hostname é preciso reiniciar):
```
$ sudo hostnamectl set-hostname <nome>.enta.pt
```

# server 

## apache 


mudar para root:
```
$ sudo su - 
```

instalar o apage:
```
apt install apache2
```

verificar se a porta 80 esta aberta:
```
ss -tln

State   Recv-Q    Send-Q    Local Address:Port    Peer Address:Port                       
LISTEN  0         4096      127.0.0.53%lo:53      0.0.0.0:*                   
LISTEN  0         128       0.0.0.0:22            0.0.0.0:*                                                             
LISTEN  0         511       *:80                  *:*                                                    
LISTEN  0         128       [::]:22               [::]:*   

```

pasta de config do apache: 
```
cd /etc/apache2/
```

Pasta do html o html:
```
cd /var/www/
```

criar 3 parastas no `/var/www/`:
```
mkdir oriental central ocidental
```

enviar texto para as pastas:
```
echo "bem vindo a www.ocidental.pt!" > ocidental/index.html
```


## Criar a sua propria página:
* Ir para a pasta:
```
cd /etc/apache2/sites-available
```
1. http
```
cp 000-default.conf example.conf
```
2. https:
```
cp default-ssl.conf exemple-ssl.conf
```
## Exemplo dos sites
* Exemplo HTTP:
```
<VirtualHost www.ocidenta.pt:80>
        
        ServerName www.ocidental.pt (descomentar) 
        
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/ocidental 
```
* Exemplo de HTTPS: 
```
<IfModule mod_ssl.c>
        <VirtualHost wwww.central.pt:443>
                ServerAdmin webmaster@localhost

                DocumentRoot /var/www/central


```

## Ativar os sites
1. Ir para a pasta `/etc/apache2/sites-enabled`. 

Desativar o site 000-default: 
```
a2dissite 000-default.conf 
```
2. Ativar o teu site:
```
a2ensite example
```
* Verificar se está ligado:
```
lrwxrwxrwx 1 root root 35 Oct 21 09:44 central-ssl.conf -> ../sites-available/central-ssl.conf
lrwxrwxrwx 1 root root 31 Oct 21 09:34 central.conf -> ../sites-available/central.conf
lrwxrwxrwx 1 root root 37 Oct 21 09:44 ocidental-ssl.conf -> ../sites-available/ocidental-ssl.conf
lrwxrwxrwx 1 root root 33 Oct 21 09:34 ocidental.conf -> ../sites-available/ocidental.conf
lrwxrwxrwx 1 root root 36 Oct 21 09:44 oriental-ssl.conf -> ../sites-available/oriental-ssl.conf
lrwxrwxrwx 1 root root 32 Oct 21 09:34 oriental.conf -> ../sites-available/oriental.conf
```

* Ativar a porta 443 para o HTTPS:
```
a2enmod ssl
```



## Para usar nomes de dominios existentes:

Alter o ficheiro dos `hosts`
```
nano /etc/hosts
```

Oque mudar no ficheiro:
```
ip_privado + dominio
```

# Instalar o Ubuntu Cliente:

Instalar o desktop:
```
sudo apt install -y xfce4 xfce4-goodies
```
Instalar o RDP, Chromium e o filezilla:
```
sudo apt install -y xrdp chromium-browser filezilla
```
Adicionar o RDP ao ssl-cert:
```
sudo adduser xrdp ssl-cert
```

adicior um user 
```
sudo adduser maria
```
```
login example
```
```
echo xfce4-session > ~/.xsession
```




