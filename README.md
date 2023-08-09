# Projeto Docker com Vue.js, Laravel 9 e PostgreSQL

Este projeto consiste em configurar um ambiente Docker com três containers para desenvolvimento: frontend em Vue.js, backend em Laravel 9 e banco de dados PostgreSQL. O Docker Compose é utilizado para orquestrar e gerenciar esses containers.

## Requisitos

Certifique-se de ter o Docker e o Docker Compose instalados em sua máquina antes de prosseguir.

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Configuração

1. Clone este repositório:

```bash
git clone https://github.com/lucasmenescal/desafio_dev_fs_jr-pl.git
cd desafio_dev_fs_jr-pl
```

2. Clone os projetos de frontend e backend:

Certifique-se de criar uma pasta chamada projeto dentro das pastas backend e frontend, e clone os repositórios correspondentes dentro dessa pasta.

```bash
cd frontend
mkdir projeto
git clone https://github.com/seu-usuario/frontend-vue.git projeto

cd ../backend
mkdir projeto
git clone https://github.com/lucasmenescal/cepinfo.git projeto
```

## Uso

Para iniciar o ambiente Docker com os containers, execute o seguinte comando na raiz do projeto:

```bash
docker-compose up -d
```
Isso criará e executará os containers em segundo plano. Certifique-se de que as portas 80 (frontend), 8000 (backend) e 5432 (PostgreSQL) estejam disponíveis em sua máquina.

## Acesso

- **Frontend Vue.js:** [http://localhost](http://localhost:8080)
- **Backend Laravel:** [http://localhost:8000](http://localhost:8000)
- **Banco de Dados PostgreSQL:**
  - **Acesso do Host**
    - **Host:** localhost
    - **Porta:** 5432
    - **Usuário:** postgres
    - **Senha:** (definida no arquivo `.env` do do projeto do backend)
  - **Acesso Interno Docker**
    - **Host:** 172.16.0.4
    - **Porta:** 5432
    - **Usuário:** postgres
    - **Senha:** (definida no arquivo `.env` do do projeto do backend)

## Encerrando o Ambiente

Para parar e remover os containers, execute:

```bash
docker-compose down
```