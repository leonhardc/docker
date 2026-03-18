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


