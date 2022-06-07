# Instalação do Odoo 
## Pré requisitos: 

Para se desenvolver Odoo, é recomendável ambiente GNU / Linux;

Conta no github: https://github.com

Utilizar como versões suportadas pela Odoo SA:

Odoo 14: Debian Buster ou Ubuntu 22.04 LTS - https://www.odoo.com/documentation/15.0/

## Iniciando 

Atualizando seu sistema!

`sudo apt-get update`

`sudo apt-get upgrade`

## Instalação do git e virtualenv

`sudo apt-get install -y git python3 nano virtualenv xz-utils wget fontconfig libfreetype6 libx11-6 libxext6 libxrender1 xfonts-75dpi`
    
Criando um projeto Odoo


## Criação de um diretório para o seu projeto 
`mkdir ~/Projects/odoo/ -p`

`cd ~/Projects/odoo`

### Dependencias de build 

`sudo apt install gcc build-essential python3-dev`

#### v15

`sudo apt install libpq-dev libxml2-dev libxslt1-dev libldap2-dev libsasl2-dev libtiff5-dev libjpeg8-dev libopenjp2-7-dev zlib1g-dev libfreetype6-dev liblcms2-dev libwebp-dev libharfbuzz-dev libfribidi-dev libxcb1-dev`

## PostgreSQL 

https://www.postgresql.org/download/

`sudo apt-get install postgresql postgresql-contrib `

whoami 

`sudo su - postgres`

`createuser -s <USUARIO>`

###  Testando
 
`createdb teste`
    
`dropdb teste`

#### Criando venv**

`python -m venv venv`

`source ./venv/bin/activate`

Para sair:

`deactivate`

### Baixe do Odoo 
https://github.com/odoo

##### Lembrar de especificar a versão
`git clone https://github.com/odoo/odoo.git ./core --branch=15.0 --depth=1`

##  Instalação das dependencias python 

`source venv/bin/activate`
    
`pip install -r core/requirements.txt``

##  Executando o Odoo 

`./odoo-bin -c odoo.conf --save --stop-after-init`

`./odoo-bin -c odoo.conf`
