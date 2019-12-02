Nesta atividade será implantado e testato o primeiro pipeline, este pipeline é bem simples e não realiza nenhuma função referente a uma aplicação, visando demonstar os fundamnetos iniciais este pipeline apenas executa comandos nos containers, em conjunto foi adicionado os passos de build e environment para que você possa ir se acostumando e buscando entender o funcionamneto de cada um. Para que o pipeline funcione realize os seguintes passos:

- Crie um novo Projeto no gitlab
- crie as variaveis `VAR01` e `DEPLOY_DEV` em modo private para o projeto
- Faça o push de todos os arquivos deste diretorio no projeto criado, abaixo há um exemplo de como realizar esta ação.

```
cd existing_folder
git init
git remote add origin {{ endereço do git do projeto }}
git add .
git commit -m "Initial commit"
git push -u origin master
```

Apos fazer o push clique na opção `CI/CD` e observe o pipeline que foi criado, veja todos os jobs sendo executado, caso um job falhe tente fazer troubleshoot visando garantir o ciclo da integração, fique a vontada para realizar modificações, como por exemplo remover o deploy do modo `manual`.
