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




