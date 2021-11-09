# Configuração da AWS

Após a isntalação do odoo em sua instancia, temos que fazer as configurações do banco de dados(Nesse caso usaremos RDS).

## Liberando Portas

Para que possamos utilizar o banco temos que liberar as portas de uso dele, tanto na instacia quanto na RDS:

* para isso iremos ter que entrar na instacia e ver o grupo de segurança:

![Grupos de Segurança](https://user-images.githubusercontent.com/59977779/140947891-c144d7bf-ffec-4db4-a12f-05fd36cf3c1a.png)

* Depois nas configurações do grupo de segurança entrar nas regras de entrada e saída:

![Regras](https://user-images.githubusercontent.com/59977779/140959768-b2752839-4166-4c64-843c-a0fed62cc3d1.png)

* Adicionar regra:

![Adicionar regra](https://user-images.githubusercontent.com/59977779/140960071-47050d6d-8da7-4883-b5cc-c1761ff73a9c.png)

* Configurar a regra:

![Configurar](https://user-images.githubusercontent.com/59977779/140960148-a5cac659-c050-40a8-8c31-01dfcffcc86a.png)

* E por fim salvar a regra:

![Salvar](https://user-images.githubusercontent.com/59977779/140960228-f4ef7f86-1696-4a98-9c37-6fcaa3a1be53.png)

Obs: O odoo não ira iniciar sem a liberação dessas portas que normalmente são 8069 para o odoo e 5432 para o Postgresql

## Arquivo de configuração

Entre por meio de SSH em sua instancia e vá para o arquivo odoo.conf.

![image](https://user-images.githubusercontent.com/59977779/140961873-47fa6ef3-da78-4784-bf6f-60f7ecce72bd.png)

E por ultimo iremos configurar os dados de conexão do RDS

![Captura de tela 2021-11-09 131402](https://user-images.githubusercontent.com/59977779/140962017-80140a6c-4d3d-4d04-b804-68a04965e966.png)

