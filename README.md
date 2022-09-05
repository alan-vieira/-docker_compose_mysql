# Docker Compose para Instalação do MySQL
## Descrição do projeto
Arquivo docker-compose para automação da instalação do MySQL no docker

## Funcionalidades do projeto
- `Funcionalidade 1`: atomatiza o processo de instalação do gerenciador do MySQL no docker.
- `Funcionalidade 2`: cria um volume para persistência dos dados.

## Aplicação
![Docker Compose](./img/docker_compose_mysql.JPG)

## Execução
Iniciando o docker-compose o parametro -d, para rodar em segundo plano
```bash
docker-compose up -d
```

Caso precise parar todos os containers do aquivo
```bash
docker-compose down
```

Para remoção do arquivo
```bash
docker-compose rm
```

## Autor

| [<img src="https://avatars.githubusercontent.com/alan-vieira" width=115><br><sub>Alan Vieira</sub>](https://github.com/alan-vieira) |
| :---: |
