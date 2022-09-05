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

Por questão de seguranão, o MySQL restringe outras conexões além da máquina local (neste caso, container Docker) por padrão. Então para podermos efetuar a conexão além da nossa máquina local, vamos alterar essa restrição.

Passo 1: Conectando-se ao servidor MySQL de dentro do container
```bash
docker exec -it my-mysql bash
```
Passo 2: Assim que estiver dentro do container, você pode se conectar ao servidor
```bash
mysql -u root -p
```
Passo 3: Crie um novo banco de dados para efetuar testes
```bash
CREATE DATABASE MYSQLTESTE;
```
Passo 4: Altere a restrição de conexão:
```bash
update mysql.user set host='%' where user='root';
```
Passo 5: Execute o seguinte comando para que as alterações no usuário root tenham efeito
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
