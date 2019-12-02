# CI/CD utilizando GitLab CI e Ansible 

Este repositorio contem todos os documentos que serão utilizados no minicurso do iftech a estrutura dos arquivos foi organizada visando se adequar a cada atividade que será realizada.

Será fornecido no dia do minicurso uma VM ubuntu 18.02 para que possa relaizar as atividades, assim como o ip de acesso ao git e a conta dos usuários 

A primeira coisa a fazer é extrair a box, o usuario e senha para acessar a vm é `ubuntu`

vamos criar uma chave SSH para o usuário, execute o seguinte comando para gerar a chave, pressione enter para todas as perguntas que serão solicitadas

```
ssh-keygen 
```

* Lembrar de criar a chave logado com o usuário ubuntu, Essa chave será utilizada posteriorimente para realizar as implantações assim como o clone do repositório.

Paar todas as atividades existirá um Readme visando explicar a atividade e auxiliar na realização, as atividades serão realizadas seguindo a seguinte ordem:

- Provisionamento
- Pipelines 02
- Pipelines 03
- Pipelines 04
- Pipelines 05

Para que possa realizar as atividades faça o clone deste repositorio para a box que foi fornecida, recomenddamos que todos os comandos sejam executados na box fornecida, caso seja necessario gere uma nova vm com a box fornecida.

