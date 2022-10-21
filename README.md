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

# server 

## apache 


mudar para root:
```
sudo su - 
```

mudar o hostname:
```
hostnamectl set-hostname <nome>.enta.pt
```

instalar o apage:
```
apt install apache2
```

verificar se a porta 80 esta aberta:
```
ss -tln
```


editar o html:
```
cd cd /var/www/html
nano index.html
```
criar as parastas:
```
mkdir oriental central ocidental
```

enviar texto para as pastas:
```
exemplo:
  echo "bem vindo a www.ocidental.pt!" > ocidental/index.html
```


config apache 
```
/etc/apache2/
|-- apache2.conf
|       `--  ports.conf
|-- mods-enabled
|       |-- *.load
|       `-- *.conf
|-- conf-enabled
|       `-- *.conf
|-- sites-enabled
|       `-- *.conf

```

Raízes do Documento  / permissoes   
```
/var/www/html
/etc/apache2/apache2.conf
```

Criar um documento e o rederecionar:
```
echo "Bem vindo a www.example.pt!" > example/index.html
```

Criar a sua propria página:
```
1.
 cd /etc/apache2/sites-available
2. http
 cp 000-default.conf example.conf
3.
  cp default-ssl.conf exemple-ssl.conf

Exemplo HTTP:

<VirtualHost www.ocidenta.pt:80>
        
        ServerName www.ocidental.pt (descomentar) 
        
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/ocidental 

Exemplo de HTTPS: 

<IfModule mod_ssl.c>
        <VirtualHost wwww.central.pt:443>
                ServerAdmin webmaster@localhost

                DocumentRoot /var/www/central


```

Ativar o website e desativar o default:
```
cd etc/apache2/sites-enabled/

a2dissite 000-default.conf 

a2ensite example
```
Para usar nomes de dominios existentes:
```
1.
nano /etc/hosts

2.
ipprivado + dominio

3.
cd /etc/apache2/sites-available

4.
nano example.conf

5. 
#ServerName www.example.com
```

Ativar o https:
```
1.
cd /etc/apache2/sites-available

2.
 cp default-ssl.conf example-ssl.conf
 
3.
<VirtualHost www.example.pt:443>
                ServerAdmin webmaster@localhost

                DocumentRoot /var/www/example
4.
a2ensite example-ssl.conf 

```

# Instalar o Ubuntu Cliente:
```
1.
sudo apt install -y xfce4 xfce4-goodies

2.
sudo apt install -y xrdp chromium-browser filezilla

3.
sudo adduser xrdp ssl-cert

4.
sudo adduser maria

5.
login example

6.
echo xfce4-session > ~/.xsession
```




