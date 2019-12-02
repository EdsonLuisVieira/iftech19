Feito o nosso primeiro Pipeline agora vamos configurar nosso primeiro playbook. Imagine algo simples que seja do seu cotidiano, mas que é necessario realizar diversas vezes, e em diversos hosts, desde instalar um apache há subir um cluster kubernetes.

Mas calma, vamos começar devagar, hahaha, vamos pensar no provisionamento de uma aplicação web simples, um webserver. Vamos provisionar um webserver de maneira agil ?

O playbook deste diretorio provisiona um LAMP em um host on-promisse, é um playbook bem simples e sem a hierarquia de diretórios, tudo isso para mostar que o ansible é muitoooo flexivel, mas lembrem sempre das boas praticas!

Provisione o LAMP, implante a aplicação e modifique o código a vontade, valide a implantação, e após o primeiro provisionamento implante novamente! veja como o ansible é inteligente, modificando apenas o necessário.

* Caso vá implantar em outro host lembre de copiar sua chave ssh para o host destino `ssh-copy-id user@server` , ou utilizar as opções `-k --ask-become-pass` em conjunto com o `ansible-playbook`

Para realizar a implantação utilize os seguintes passos:

```
- modifique o arquivo hosts para se adequar ao ip do ser servidor
- Se for utilizar chaves como forma de autenticação utillize o comando abaixo:
  ansible-playbook -i hosts playbook.yml
- Se for utilizar senha como forma de autenticação utillize o comando abaixo:
  ansible-playbook -i hosts playbook.yml -k --ask-become-pass
```
ATENÇÂO: Lembre que no playbook há uma task para modificar a senha padrão do banco de dados, após a primeira implantação lembre de atualizar a senha no arquivo.

Após realizar a implantação host in host, que tal montar um gitlab-ci para implantar o webserver ?
Tente montar o pipeline, você pode utilizar o pipeline do passo anterior mas no job deploy substitua pelo job a seguir

```
deploy_dev:
  stage: deploy-dev
  image: edsonlvalmeida/ansible:1.0
  script:
    - echo "Deploy to staging server"
    - echo "$private_key" > key && chmod 400 key
    - eval "$(ssh-agent -s)"
    - ssh-add key
    - export ANSIBLE_HOST_KEY_CHECKING=False
    - ansible-playbook -i hosts playbook.yml
  environment:
    name: deploy-dev
    url: "$ENV_PROD"
  when: manual
  only:
  - master
```

Para realizar a adaptação utilize os seguintes passos:

```
- modifique o arquivo hosts para se adequar ao ip do ser servidor
- Neste caso só é possivel utilizar chave SSh para isso crie uma variavel privada `private-key` contendo sua chave privada
- Crie a variavel privada `ENV_PROD` contendo a url do futuro webserver, como por exemplo `http://192.168.99.12`
```

