# Docker

## Apresentação

Este repositorio tem o intuito somente de estudo e anotação sobre docker. Qualquer conhecimento que você encontrar aqui poderá ser encontrado em sites especializados, documentações e outros meios de compartilhamento de conhecimento.

## Comandos Docker

### Comandos: Imagens

```bash
$ docker image ls # lista todas as imagens no host
```

```bash
$ docker images # versão abreviada do comando acima
```

```bash
$ docker pull {usuario}/{nome-da-imagem}:{tag} # baixar uma imagem do dockerhub ou outro hub docker
```

### Comandos: Containers

```bash
$ docker container run {imagem} # inicia um container
```

```bash
$ docker run {imagem} # inicia um container
```

```bash
$ docker run -d {imagem} ## inicia um container mas sem travar o terminal
```

```bash
$ docker run -d -p {posta-host}:{posta-container} # roda um container redirecionando a porta do host para uma determinada porta do container. obs: 8080:80
```

```bash
$ docker ps # mostra todos os containers que estao rodando
```

```bash
$ docker ps -a # mostra todos os containers
```

```bash
$ docker stop {id-container} # para o container
```

```bash
$ docker logs {id-container} # logs do container
```

```bash
$ docker logs {id-container} -i # logs do container em tempo real
```

```bash
$ docker container stats # mostra estatisticas do container em comparacao as estatisticas do host
```

```bash
$ docker container pause {id-container} # Pausa um container em execução
```

```bash
$ docker container enpause {id-container} # Despausa um container pausado
```

```bash
$ docker container top {id-container} # lista os processos do container
$ docker top {id-container} # faz a mesma coisa do comando anterior
```

```bash
$ docker stop {id-container} # para um container
```

```bash
$ docker container start {id-container} # starta container parado
```

```bash
$ docker exec {id-container} {comando} # Executa comandos dentro do container. Lembrando que somente comandos que existem no container.
```

```bash
$ docker exec -it {id-container} {comando} # Taxar um comando no modo iterativo
# Ex.:
$ docker exec -it {id-container} /bin/sh
# ou 
$ docker exec -it {id-container} /bin/bash
```

```bash
$ docker rm {id-container} # remover um container
$ docker rm -f {id-container} # parar e remover o container, caso o container estiver rodando.
```

```bash
$ docker container prune # remove todos os containers parados
```


