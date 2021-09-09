# Controle de Versão

## Introdução ao controle de Versão

### Iniciando o seu projeto

git init

git add .gitignore

git commit / gitg

### Submodule

git submodule add <URL> FOLDER

#### Ou clone primeiro e adicione depois

git clone git@github.com:odoo/odoo.git core --depth=1 --branch=VERSAO

git submodule add ./core

### Enviando para o github

git add odoo.conf

git remote add origin <URL>

git push origin master

### Replicando o ambiente

#### Download do repositório

git clone --recursive URL

git clone --recursive URL --shallow-submodules # Opção mais rápida, com consequências

#### Dependências de Build

sh build.sh

### Virtualenv

virtualenv venv -p python3

#### Python Requirements

pip install -r requirements

### Adaptando o arquivo de configuração

#### Caminhos relativos

nano odoo.conf

-addons_path = /home/mileo/Projetos/odoo/core/odoo/addons,/home/mileo/Projetos/odoo/core/addons,/home/mileo/Proje ...

+addons_path = ./core/odoo/addons,./core/addons,./partner-contact

#### Alteração do diretório filestore

mkdir filestore

nano odoo.conf

- data_dir = /home/mileo/.local/share/Odoo

+ data_dir = ./filestore

nano .gitignore

+ filesore/

### Atualizando um ambiente existe

#### Sobrescrevendo as mudanças locais

git fetch REMOTO

git reset --hard REMOTO/branch

git submodule update

### Requirements do repositório

#### Requirements do seu projeto

###### Outros projetos as vezes também tem dependências

git clone https://github.com/oca/l10n-brazil.git --branch=VERSAO

git submodule add ./l10n-brazil

pip install -r l10n-brazil/requirements.txt

pip freeze > requirements.txt

pip install -r requirements.txt

[commit ...]

## Resumo

git init # inicia o repositório

git remote add REMOTE_NAME URL # Adiciona url remota

git push REMOTE_NAME branch # envia branch local para o remoto

git clone URL # Clona o repositório

git clone --recursive URL # Clona o repositório e os submodulos

git submodule add URL PASTA # Adiciona submoduo ao repositório principal

git submodule init # Inicializa os submodulos não inicializados

git submodule update # Atualiza seus submodulos com a versão do remoto

tig Interface de texto para o GIT

gitg Interface gráfica para o GIT

git add ARQUIVO # Adiciona conteudo do arquivo para o index

git commit -v  # Abre a interface de commit com as diferenças

git commit -va # Identico ao anterior + git add em arquivos já monitorados
