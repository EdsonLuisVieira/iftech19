# Fazendo deploy com docker

No passo `provisionamento` já provisionamos a maquina para realizar deploy com docker, assim como já montamos nosso primeiro pipeline além disso já adaptamos um deploy via playbook para ser implantado com o gitlab, que tal implantar uma API utilizando container docker?
para este passo vamos utilizar a aplicação de um grande Dev amigo meu, Joeverson Santos, o código original está no github, a aplicação utilizada nesta implantação foi modificada para se adaptar ao nosso cenário, antes de implantar leia o readme da aplicação no github e busque entender a estrutura e arquitetura da aplicação.

- [ Aplicação base-api-nosql](https://github.com/Joeverson/base-api-nosql)

A primeira coisa a se fazer é criar um novo projeto no gitlab, caso não tenha adicionado a chave no passo anterior, essa é a hora! adicione a chave em uma variável privada que possa ser utilizada no pipeline, assim como na atividade 02 é necassário fazer o push dos arquivos no repositório criado, antes de fazer o push observe a estrutura dos arquivos, como o pipeline funciona, quais comandos ele executa e como o playbook é executado, observe as roles e as tags que podem ser utilizadas para adaptar as variáveis e criar novos ambientes de deploy, antes de implantar, crie todas as variáveis que estão declaradas no arquivo de CI.

Uma novidade neste pipeline é a integração com o SonarQube, uma ferramneta poderosa para análise de código, encontarndo bugs e vulnerabilidades na aplicação, seu funcionamnto vai ser explicado durante o minicurso.

