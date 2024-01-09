# Nome do Projeto

Descrição concisa e informativa sobre o projeto.

## Pré-requisitos

- Node.js (v18.x)
- npm ou yarn
- Docker e Docker Compose (para Prisma, se estiver usando um banco de dados Dockerizado)
- OpenSSL (para gerar chaves PEM)

## Configuração do Ambiente

1. **Clone este repositório.**

    ```bash
    git clone https://github.com/guilherme1-jgp/delliv-repo.git
    cd nome-do-projeto
    ```

2. **Instale as dependências:**

    ```bash
    npm install
    ```

    ou

    ```bash
    yarn
    ```

3. **Copie o arquivo de exemplo de configuração do Prisma:**

    ```bash
    cp prisma/.env.example prisma/.env
    ```

    Edite `prisma/.env` conforme necessário.

4. **Inicialize o banco de dados com Prisma:**

    ```bash
    npx prisma db push
    ```

## Gerando Chaves PEM

Para autenticação segura, você precisará de um par de chaves privada e pública no formato PEM. Use o OpenSSL para gerar essas chaves.

1. **Gere uma chave privada (private.pem):**

    ```bash
    openssl genpkey -algorithm RSA -out private.pem
    ```

2. **Extraia a chave pública correspondente (public.pem):**

    ```bash
    openssl rsa -pubout -in private.pem -out public.pem
    ```

    Guarde esses arquivos com segurança. A chave privada (`private.pem`) deve ser mantida em segredo, enquanto a chave pública (`public.pem`) pode ser compartilhada para fins de autenticação.

## Executando a Aplicação

- **Inicie a aplicação:**

    ```bash
    npm run start
    ```

    ou

    ```bash
    yarn start
    ```

- Acesse a aplicação em [http://localhost:3000](http://localhost:3000).

## Comandos Úteis

- **Executar Testes:**

    ```bash
    npm run test:watch
    ```

 **Construa as imagens e inicie os contêineres:**

    ```bash
    docker-compose up
    ```