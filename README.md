# ron-user-api
A API to user authentication control.

## Introdução

Ron-API nasceu para controle de usuários contendo funcionalidades de cadastramento e controle de autenticação de usuários. Esse documento compreende desde sua instalação até o modelo de suas requisições. Este manual se restringe ao ambiente de desenvolvimento.

## Pré-requisitos para funcionamento da API

Nodejs version 12+: 
https://nodejs.org/en/download/

Python 2: 
https://www.python.org/download/releases/2.0/#download

Visual Studio 2019 versão 16 for C++ Development: 
https://visualstudio.microsoft.com/pt-br/vs/features/cplusplus/

Git version 2: 
https://git-scm.com/downloads

## Instalação

No terminal CMD, acessando o diretório desejado acione o comando: git clone https://github.com/RafaeloDuarte/ron-api.git
No mesmo terminal acesse a pasta criada ‘ron-api’ com o comando: cd ron-api
Em seguida comando ‘npm install’ para criar a pasta node_modules e instalar todas as dependências necessárias.
Coloque o servidor no ar com o comando ‘npm start’

## Arquitetura das requisições

* ### Cadastro de Usuário

Verbo POST no endereço host/v1/api/usuarios/register
O corpo da requisição deve estar em formato x-www-form-urlencoded
Deve ter as chaves e valores nessa formação:

{
    email: email@email.com,
    password: senha,
    nome: Nome
}

A resposta da requisição será os dados cadastrados e o token de autenticação para que o usuário já esteja logado e possa usufruir dos serviços:

* ### Login

Para Login o verbo é POST e a url é host/v1/api/usuarios/login
O corpo da requisição deve estar em formato x-www-form-urlencoded
Deve ter as chaves e valores nessa formação:

{
    email: email@email.com,
    password: senha
}

A resposta da requisição será os dados cadastrados e o token de autenticação para que o usuário já esteja logado e possa usufruir dos serviços:

* ### Update

Para qualquer alteração dos dados de usuário é necessário estar logado ou seja passar o token gerado no login na head da requisição como o exemplo abaixo:
 
O verbo usado será PUT e a requisição deve ser feita para host/v1/api/usuarios.

A resposta será com os dados alterados e um novo token. 

* ### Delete

Para deletar um usuário deve-se estar logado como este usuário.
O verbo para tal é DELETE e o caminho da requisição é host/v1/api/usuarios
