# Backend Challenge BackEnd Pleno

#### Introdução
O desafio consiste em criar uma API REST utilizando os dados do Open Food Facts(um banco de dados aberto com informações nutricionais de diversos alimentos).

O projeto tem como objetivo dar suporte a equipe de nutricionistas de uma empresa para que eles possam revisar de maneira rápida a informação nutricional dos alimentos que os usuários publicam pela aplicação móvel.


#### Antes de começar
- O projeto deve ser utilizado a Linguagem NodeJs ou PHP.
- Considere o prazo de entrega de dias a partir do recebimento do desafio.
- Documentar todo o processo de investigação para o desenvolvimento da atividade (README.md no seu repositório); os resultados destas tarefas são tão importantes do que o seu processo de pensamento e decisões à medida que as completa, por isso tente documentar e apresentar os seus hipóteses e decisões na medida do possível.
- A entrega deverá ser disponibilizada no Github do candidato com a visibilidade pública e colocar esse readme como referência.


#### O projeto
- Criar um banco de dados SQL ou NoSQL
- Criar uma REST API com as melhores práticas de desenvolvimento, Design Patterns, SOLID e DDD.
- Integrar a API com o banco de dados criado para persistir os dados. Recomendável usar Drivers oficiais para integração com o DB
- Desenvolver Testes Unitários


#### Modelo de Dados
Para modelagem do banco de dados, consulte o arquivo data/products.json no repositório. Considere criar um campo de controle interno que alimente o status do registro:
- data e hora da importação do item
- status do item importado


#### Sistema do CRON
O projeto também deve conter um sistema de atualização que irá importar os dados para a Base de Dados com a versão mais recente dos dados dos alimentos uma vez ao dia. Adicionar o horário de execuçao nos arquivos de configuração.

A lista de arquivos do Open Food, pode ser encontrada na pasta /data.
Os campos dos dados podem ser encontrado no arquivo /data/data-fields.txt

É recomendável a utilização de um sistema de controle secundário para gerenciamento do histórico de importações e facilitar a validação durante a execução.

Considerações
- Todos os produtos deverão ter os campos de controle de importação e status.
- Limitar a importação a somente 100 produtos de cada arquivo.


#### API REST
Criar um CRUD com os seguintes endpoints:
- GET / : Detalhes da API, se conexão leitura e escritura com a base de dados está OK, horário da última vez que o CRON foi executado, tempo online e uso de memória.
- PUT /products/{code} : Será responsável por receber atualizações do Projeto Web
- DELETE /products/{code} : Mudar o status do produto para deleted
- GET /products/{code} : Obter a informação somente de um produto da base de dados
- GET /products : Listar todos os produtos da base de dados, adicionar sistema de paginação para não sobrecarregar o REQUEST


#### Diferenciais
- Configuração de um endpoint de busca com Elastic Search ou similares;
- Configurar Docker no Projeto para facilitar o Deploy da equipe de DevOps;
- Configurar um sistema de alerta se tem algum falho durante o Sync dos produtos;
- Descrever a documentação da API utilizando o conceito de Open API 3.0;
- Escrever Unit Tests para os endpoints GET e PUT do CRUD;
- Escrever um esquema de segurança utilizando API KEY nos endpoints. Ref: https://learning.postman.com/docs/sending-requests/authorization/#api-key


#### Readme do Repositório
- Deve conter o título do projeto
- Uma descrição sobre o projeto em frase
- Deve conter uma lista com linguagem, framework e/ou tecnologias usadas
- Como instalar e usar o projeto (instruções)
- Não esqueça o .gitignore

