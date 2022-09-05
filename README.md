# Docker Compose para Instalação do MySQL
## Descrição do projeto
Arquivo docker-compose para automação da instalação do MySQL no docker

## Funcionalidades do projeto
- `Funcionalidade 1`: atomatiza o processo de instalação do gerenciador do MySQL no docker.
- `Funcionalidade 2`: cria um volume para persistência dos dados.

## Aplicação
![Docker Compose](./img/docker_compose_mysql.JPG)

## Execução
Iniciando o docker-compose com o parametro -d, para rodar em segundo plano
```bash
docker-compose up -d
```

Conectando-se ao servidor MySQL de dentro do container
```bash
docker exec -it my-mysql bash
```
Assim que estiver dentro do container, você pode se conectar ao servidor
```bash
mysql -u root -p
```
Crie um novo banco de dados para efetuar testes
```bash
CREATE DATABASE MYSQLTESTE;
```

Por padrão, o MySQL restringe outras conexões além da máquina local (neste caso, contêiner Docker) por razões de segurança. Portanto, para se conectar a partir da máquina local, você deve alterar a restrição de conexão:
```bash
update mysql.user set host='%' where user='root';
```
A seguir, execute o seguinte para que as alterações no usuário root tenham efeito:
```bash
FLUSH PRIVILEGES;
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
