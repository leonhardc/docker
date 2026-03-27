# Docker

## Apresentação

Este repositorio tem o intuito somente de estudo e anotação sobre docker. Qualquer conhecimento que você encontrar aqui poderá ser encontrado em sites especializados, documentações e outros meios de compartilhamento de conhecimento.

## Comandos Docker

### Comandos: Imagens

```bash
# lista todas as imagens no host
$ docker image ls 
```

```bash
# versão abreviada do comando acima
$ docker images 
```

```bash
# baixar uma imagem do dockerhub ou outro hub docker
$ docker pull {usuario}/{nome-da-imagem}:{tag} 
```

### Comandos: Containers

```bash
# inicia um container
$ docker container run {imagem} 
```

```bash
# inicia um container
$ docker run {imagem} 
```

```bash
# inicia um container mas sem travar o terminal
$ docker run -d {imagem} 
```

```bash
# roda um container redirecionando a porta do host para 
# uma determinada porta do container. Ex: 8080:80
$ docker run -d -p {posta-host}:{posta-container} 
```

```bash
# mostra todos os containers que estao rodando
$ docker ps 
```

```bash
# mostra todos os containers
$ docker ps -a 
```

```bash
# para o container
$ docker stop {id-container} 
```

```bash
# logs do container
$ docker logs {id-container} 
```

```bash
# logs do container em tempo real
$ docker logs {id-container} -i 
```

```bash
# mostra estatisticas do container em comparacao as estatisticas do host
$ docker container stats 
```

```bash
# Pausa um container em execução
$ docker container pause {id-container} 
```

```bash
# Despausa um container pausado
$ docker container enpause {id-container} 
```

```bash
# lista os processos do container
$ docker container top {id-container} 
 # faz a mesma coisa do comando anterior
$ docker top {id-container}
```

```bash
 # parar um container
$ docker stop {id-container}
```

```bash
# starta container parado
$ docker container start {id-container} 
```

```bash
# Executa comandos dentro do container. Lembrando que 
# somente comandos que existem no container.
$ docker exec {id-container} {comando} 
```

```bash
# Taxar um comando no modo iterativo
$ docker exec -it {id-container} {comando} 
# Ex.:
$ docker exec -it {id-container} /bin/sh
# ou 
$ docker exec -it {id-container} /bin/bash
```

```bash
# remover um container
$ docker rm {id-container} 
# parar e remover o container, caso o container 
# estiver rodando.
$ docker rm -f {id-container} 
```

```bash
# remove todos os containers parados
$ docker container prune 
```

### Bridge

```bash
# Listar as redes docker
$ docker network ls
```

```bash
# Cria uma rede docker chamada demo
$ docker network create demo
```

```bash
# Inspedionar uma rede
$ docker inspect {id-network}
# ou
$ docker network inspect {id-network}
```

```bash
# conectar uma rede em um container
$ docker network connect {rede} {container}
```

```bash
# conectar uma rede em um container agora configurando um alias para
# o container. Sendo possivel agora chamar esse container pelo alias
# pela rede.
$ docker network connect --alias={alias-container} {rede} {container}
```

```bash
# Desconectar uma rede em um container
$ docker network disconnect {rede} {container}
```

### Volumes

```bash
# Criar um volume docker
$ docker volume create [{nome-do-volume}]
```
```bash
# Listar os volumes docker
$ docker volume ls
```
### Criando Imagens

O exemplo abaixo é de uma imagem criada para uma aplicação Django, que é o que estou atualmente trabalhando.

```dockerfile
FROM python:3.10.12

WORKDIR /app

COPY requirements.txt /app

RUN pip install -r requirements.txt

COPY . .

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
```

Passo a passo vou explicar cada um dos comandos:

* Em `FROM python:3.10.12` definimos qual imagem usaremos de base para a imagem que estamos criando. No meu caso é o `python:3.10.12`;
* `WORKDIR /app` se refere a qual sera o meu diretorio padrao, ou diretorio de trabalho, dentro da nossa imagem;
* `COPY requirements.txt /app` é um comando para copiar o arquivo `requirements.txt` para o diretorio `/app` dentro da imagem;
* `RUN pip install -r requirements.txt` é para rodar um comando na hora que voce esta montando a imagem. No caso o comando é `pip install -r requirements.txt`;


