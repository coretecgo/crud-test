# crud-test

<p align="center"><a href="hhttps://www.coretiexpert.com.br/" target="_blank"><img src="https://coretiexpert.com.br/wp-content/themes/coretecnologia/assets/images/core-ti-expert-vert.png" width="160"></a></p>


## Teste para Desenvolvedor Back-end

Seja muito bem-vindo(a), futuro Developer da Adoorei.

Nós, recrutadores juntamente com a nossa equipe de DEV, desenvolvemos um teste prático para avaliar tecnicamente todos os candidatos que estão participando do nosso processo seletivo para a vaga de Desenvolvimento Back End.

Boa sorte!


## Objetivo

- Por meio de um API REST em (Qualquer linguagem), crie uma CRUD.
- Após a execução da etapa anterior, crie um comando doker-compose que ira gerar o banco de dados, rodar seeders e tudo que você projetou.

## Primeiro passo

Para iniciar o desenvolvimento, você deverá criar um Fork desse projeto. Obs: Não serão aceitas Pull Requests (PRs) 

## Configuração do ambiente

Para iniciar essa etapa de configuração do ambiente, é obrigatório ter o [Docker](https://docs.docker.com/desktop/ "Docker") instalado em sua máquina. 

Crie um container utilizando docker capaz de executar o seu projeto. Dica para iniciar seu arquivo docker:

```
$ docker compose up -d
```

A aplicação deve rodar acessando localhost:8000 no seu navegador para visualizar a aplicação.

## Funcionalidades a serem implementadas.
Neste teste, seu objetivo será desenvolver uma API REST.  Por tanto você deverá focar em construir apenas uma API, não se preocupe com a parte visual ou outras coisas que não sejam pertinentes.

##### CRUD de produtos
Você deverá desenvolver as principais operações para o gerenciamento de um catálogo de produtos, que são:
- Criação
- Listagem
- Atualização
- Exclusão

É necessário que o produto tenha a seguinte estrutura:
Campo       | Tipo      | Obrigatório   | Pode se repetir
----------- | :------:  | :------:      | :------:
id          | int       | true          | false
name        | string    | true          | false        
price       | float     | true          | true
description  | text      | true          | true
category    | string    | true          | true
image_url   | url       | false         | true

Os endpoints para criação e atualização devem seguir o  formato do payload abaixo, **É importante que todos os atributos passem por uma camada de validação para que os dados sejam armazenados na base de dados da forma correta.**

```json
{
    "name": "product name",
    "price": 781.22,
    "description": "Lorenzo Ipsulum",
    "category": "test",
    "image_url": "https://fakestoreapi.com/img/71li-ujtlUL._AC_UX679_.jpg"
}

```

##### Busca de produtos
É necessário que o sistema tenha algumas funcionalidades de buscas para a manutenção do catálogo de produtos, sendo elas: 

- Busca pelos campos name e category (trazer resultados que batem com ambos os campos).
- Busca por uma categoria específica.
- Busca de produtos com e sem imagem.
- Buscar um produto pelo seu ID.

##### Importação de produtos de uma API externa
Crie um comando que buscará produtos numa API externa e armazenará todos os resultados dentro de sua base de dados. Essa aplicação é necessária para que o sistema consiga importar produtos que estão em outro serviço. Sugerimos criar um comando artisan como abaixo:

`php artisan products:import`

Esse comando deverá ter uma opção de importar um único produto da API externa, que será encontrado através de um ID externo.

`php artisan products:import --id=123`

Utilize a seguinte API para importar os produtos: https://fakestoreapi.com/docs


------------



É isso!. Ficamos muito felizes com a sua aplicação para esse Teste. Estamos à sua disposição para tirar qualquer dúvida. Boa sorte! 😉
