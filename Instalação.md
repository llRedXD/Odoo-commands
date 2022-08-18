# Instalação do Odoo 
## Pré requisitos: 

Para se desenvolver Odoo, é recomendável ambiente GNU / Linux;

Conta no github: https://github.com

Utilizar como versões suportadas pela Odoo SA:

Odoo 15: Debian Buster ou Ubuntu 22.04 LTS - https://www.odoo.com/documentation/15.0/

## Iniciando 

Atualizando seu sistema!

`sudo apt-get update`

`sudo apt-get upgrade -y`

## Criação de um diretório para o seu projeto 
`mkdir ~/Projects/odoo/ -p`

`cd ~/Projects/odoo`

### Dependencias de build 

`sudo apt install gcc build-essential -y`

#### v15

`sudo apt install python3-pip  wget python3-dev python3-venv python3-wheel libxml2-dev libpq-dev libjpeg8-dev liblcms2-dev libxslt1-dev zlib1g-dev libsasl2-dev libldap2-dev build-essential git libssl-dev libffi-dev libmysqlclient-dev libjpeg-dev libblas-dev libatlas-base-dev -y`

## PostgreSQL 

https://www.postgresql.org/download/

`sudo apt-get install postgresql postgresql-contrib -y`

whoami 

`sudo su - postgres`

`createuser -s <USUARIO>`

###  Testando
 
`createdb teste`
    
`dropdb teste`

### Wkhymltopdf

`echo "deb http://security.ubuntu.com/ubuntu impish-security main" | sudo tee /etc/apt/sources.list.d/impish-security.list`

`sudo apt-get update`

`sudo apt-get install libssl1.1 -y`


#### Criando venv**

`python -m venv .venv`

`source ./.venv/bin/activate`

Para sair:

`deactivate`

### Baixe do Odoo 
https://github.com/odoo

##### Lembrar de especificar a versão
`git clone https://github.com/odoo/odoo.git ./core --branch 15.0 --depth 1`

##  Instalação das dependencias python 

`source venv/bin/activate`
    
`pip install -r core/requirements.txt`

##  Executando o Odoo 

`./odoo-bin -c odoo.conf --save --stop-after-init`

`./odoo-bin -c odoo.conf`
