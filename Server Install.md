# Instalação do Odoo 14 AWS
## Pré requisitos: 

Para se desenvolver Odoo, é recomendável ambiente GNU / Linux Instancia;

Conta no github: https://github.com

## Dependências: 

GNU / Linux;

PostgreSQL;

Bibliotecas C;

Python 3 e Bibliotecas que estendem uma biblioteca padrão;

Outras dependências (relatórios e outros);

## Iniciando 

Atualizando seu sistema!

`sudo apt-get update`

`sudo apt-get upgrade`

## Instalação do git e virtualenv

sudo apt-get install -y git python3 nano virtualenv xz-utils wget fontconfig libfreetype6 libx11-6 libxext6 libxrender1 xfonts-75dpi gitg

## Criação de um diretório para o seu projeto 
`mkdir ~/Projects/odoo/ -p`

`cd ~/Projects/odoo`

Iniciando o Controle de versão 

`git init`

`git status`

`git add .`

`git commit - m "Nome do commit"`

### Dependencias de build 

`sudo apt install gcc build-essential python3-dev`

#### v14

`sudo apt install libpq-dev libxml2-dev libxslt1-dev libldap2-dev libsasl2-dev libtiff5-dev libjpeg8-dev libopenjp2-7-dev zlib1g-dev libfreetype6-dev liblcms2-dev libwebp-dev libharfbuzz-dev libfribidi-dev libxcb1-dev`

## PostgreSQL 

Aqui iremos somente instalar o client para que possamos conectar com outro servidor ou um RDS.

`sudo apt-get install postgresql-client`

##  Ambientes virtuais Python 

Ambientes virtuais de Python, ou virtualenv são ambientes de trabalhos python eleição.

Permitir aos desenvolvedores trabalharem com diferentes versões de bibliotecas python instaladas.

É possivel criar quantos ambientes principais precisos;

#### v14 - 3.6 ou superior**

`virtualenv venv --python=python3`

`source bin/activate`

Para sair:

`deactivate`

### Baixe do Odoo 
https://github.com/odoo

Odoo core, imagem docker e entre outros

##### Lembrar de especificar a versão
`git clone --branch=14.0 --depth=1 https://github.com/odoo/odoo.git ./core`

##  Instalação das dependencias python 
    
`(venv) pip install -r core/requirements.txt`

##  Executando o Odoo 

`(venv) ./odoo-bin -c odoo.conf --save --stop-after-init`

`(venv) ./odoo-bin -c odoo.conf`
