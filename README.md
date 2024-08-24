
# Projeto de Container com Mongo e Mongo Express
Autor: [Jeferson Schlarski](https://github.com/Jefschlarski)

Este projeto configura um ambiente de container Docker que inclui um banco de dados Mongo e uma interface de administração via Mongo Express.

## Configuração do Ambiente


O arquivo `.env` deve ser configurado com as seguintes variáveis de ambiente:

### Variáveis de Ambiente

env:

```bash
MONGO_ROOT_USERNAME=root
```
```bash
MONGO_ROOT_PASSWORD=example
```
```bash
MONGO_EXTERNAL_PORT=27018
```
```bash
MONGO_INTERNAL_PORT=27017
```

```bash
MONGO_EXPRESS_ADMIN_USERNAME=admin
```
```bash
MONGO_EXPRESS_ADMIN_PASSWORD=admin
```
```bash
MONGO_EXPRESS_USER_USERNAME=user
```
```bash
MONGO_EXPRESS_USER_PASSWORD=user
```
```bash
MONGO_EXPRESS_PORTS=8081:8081
```

### Descrição das Variáveis de Ambiente

- `MONGO_ROOT_USERNAME`: Define o usuário root do MongoDB. No caso, está definido como `root`.
- `MONGO_ROOT_PASSWORD`: Define a senha do usuário root do MongoDB. Neste exemplo, a senha é `example`.
- `MONGO_EXTERNAL_PORT`: Define a porta externa do MongoDB. Que nesse caos é a `27018`.
- `MONGO_INTERNAL_PORT`: Define a porta interna do MongoDB. Que nesse caso é a `27017`.

- `MONGO_EXPRESS_ADMIN_USERNAME`: Define o usuário administrador do Mongo Express. No caso, está definido como `admin`.
- `MONGO_EXPRESS_ADMIN_PASSWORD`: Define a senha do usuário administrador do Mongo Express. Neste exemplo, a senha é `admin`.
- `MONGO_EXPRESS_USER_USERNAME`: Define o usuário do Mongo Express. No caso, está definido como `user`.
- `MONGO_EXPRESS_USER_PASSWORD`: Define a senha do usuário do Mongo Express. Neste exemplo, a senha é `user`.
- `MONGO_EXPRESS_PORTS`: Mapeamento de portas do Mongo Express. A configuração `8081:8081` mapeia a porta `8081` do host para a porta `8081` do container, onde o Mongo Express estará acessível.

## Uso


### Clone do Repositório

Clone o repositório:

```bash
git clone https://github.com/Jefschlarski/docker-mongo-me.git
```
```bash
cd docker-mongo-me
```

### Configuração do Arquivo `.env`

Certifique-se de que o arquivo `.env` esteja configurado conforme mostrado acima.

### Subir os Containers

Suba os containers:

```bash
docker-compose up -d
```
### Acessar o Mongo Express

Acesse o Mongo Express: Abra o navegador e acesse `http://localhost:8081/` e realize o login utilizando o usuario e senha configurado no .env.

### Conectar ao MongoDb

Conecte ao MongoDB:

-   Host: `localhost` ou `mongo`(Nome do container Mongo) caso esteja rodando a aplicação que ira se conectar no mongodb em um container utilizando a mesma network
-   Porta: `27018`
-   Usuário: `root`
-   Senha: `example`
-   String completa: `mongodb://root:example@localhost:27018/<nome do banco>`

## Encerrando os Containers


Para encerrar e remover os containers, utilize:

```bash
docker-compose down
```
## Considerações Finais


Este setup oferece um ambiente de desenvolvimento rápido para trabalhar com Mongo e gerenciar o banco de dados usando o Mango Express. Certifique-se de ajustar as configurações de acordo com suas necessidades específicas de projeto.


## Referencias

[DOCS DOCKER](https://docs.docker.com)

[MONGO DOCKER HUB](https://hub.docker.com/_/mongo)

[MONGO EXPRESS DOCKER HUB](https://hub.docker.com/_/mongo-express)
