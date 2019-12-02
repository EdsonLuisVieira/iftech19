# Provisionando ambiante

* Para Instalar o ansilbe há diversas maneiras, conforme pose sem observado em ["Instalando o Ansible"](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) para nosso cenario vamos instalar usando o pip, para isto execute os comandos abaixo:

````
apt update -y && apt upgrade -y && apt install -y sshpass
pip install ansible
````

Instalar runner

````
- curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh | sudo bash
- apt install gitlab-runner=11.7.0
````

Nos proximos passos será necessario utilizar o docker e o docker-compose, nada mais justo do que já preparar o ambiente com um playbook, antes de implantar tente entender o que cada passo realiza e como ele valida as operações, cada linha do playbook será explicada durante o minicurso, vale salientar que se caso você utilize a mesma maquina para executar o playbook e ser provisionada altere o `hosts` para `127.0.0.1` e o `connection` para `localhost`, caso vá provisionar outro host modifique o `hosts` para o grupo desejado no arquivo `hosts` e comente a opção `connection`, abaixo há um exemplo das duas opões:


* Provisomento local

````
  - hosts: 127.0.0.1
    connection: local
````

* Provisionando outro host

````
  - hosts: docker
#   connection: local
````

Em seguida digite o comando abaixo no diretorio que contem o playbook

````
ansible-playbook -i hosts playbook.yml -k
````


