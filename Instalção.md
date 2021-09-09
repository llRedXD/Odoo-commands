# Instalação do Odoo ¶
## Pré requisitos: 

Para se desenvolver Odoo, é recomendável ambiente GNU / Linux;

Conta no github: https://github.com

Utilizar como versões suportadas pela Odoo SA:

Odoo 12: Debian Stretch ou Ubuntu 18.04 LTS - https://www.odoo.com/documentation/12.0/

Odoo 14: Debian Buster ou Ubuntu 20.04 LTS - https://www.odoo.com/documentation/14.0/

## Dependências: 

GNU / Linux;

PostgreSQL;

Bibliotecas C;

Python 3 e Bibliotecas que estendem uma biblioteca padrão;

Outras dependências (relatórios e outros);

## Iniciando 

Atualizando seu sistema!

sudo apt-get update

sudo apt-get upgrade

## Instalação do git e virtualenv

sudo apt-get install -y git python3 nano virtualenv xz-utils \
    wget fontconfig libfreetype6 libx11-6 libxext6 libxrender1 xfonts-75dpi gitg
    
Criando um projeto Odoo

### Múltiplos:

Repositórios / Projetos;

Módulos Odoo;

Dependências;

Configurações;

## Criação de um diretório para o seu projeto 
mkdir ~/Projects/odoo/ -p

cd ~/Projects/odoo

Iniciando o Controle de versão 

git init

wget https://raw.githubusercontent.com/github/gitignore/master/Python.gitignore

mv Python.gitignore .gitignore

git add -f .gitignore

gitg

### Dependencias de build 

sudo apt install gcc build-essential python3-dev

#### v12

sudo apt install libpq-dev libxml2-dev libxslt1-dev libldap2-dev libsasl2-dev \
     libzip-dev libssl-dev

#### v14

sudo apt install libpq-dev libxml2-dev libxslt1-dev libldap2-dev libsasl2-dev \
    libtiff5-dev libjpeg8-dev libopenjp2-7-dev zlib1g-dev libfreetype6-dev \
    liblcms2-dev libwebp-dev libharfbuzz-dev libfribidi-dev libxcb1-dev

## PostgreSQL 

https://www.postgresql.org/download/

sudo apt-get install postgresql postgresql-contrib
whoami
sudo su - postgres
createuser -s <USUARIO>

###  Testando
 
createdb teste
dropdb teste

##  Ambientes virtuais Python 

Ambientes virtuais de Python, ou virtualenv são ambientes de trabalhos python eleição.

Permitir aos desenvolvedores trabalharem com diferentes versões de bibliotecas python instaladas.

É possivel criar quantos ambientes principais precisos;

Documentação oficial

python3 --version

##### v12 - 3.5 ou superior**

virtualenv venv --python=python3

#### v14 - 3.6 ou superior**

virtualenv venv --python=python3

source bin/activate

Para sair:

deactivate

### Baixe do Odoo 
https://github.com/odoo

Odoo core, imagem docker e entre outros

##### Lembrar de especificar a versão
git submudule add https://github.com/odoo/odoo.git ./core
gitg

##  Instalação das dependencias python 

source venv/bin/activate
    
(odoo) pip install -r core/requirements.txt

##  Executando o Odoo 

(odoo) ./odoo-bin -c odoo.conf --save --stop-after-init.0

(odoo) ./odoo-bin -c odoo.conf
