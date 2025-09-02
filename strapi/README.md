# SciSci Backend (Strapi)

Este é o backend do projeto SciSci, desenvolvido com [Strapi](https://strapi.io/) e banco de dados PostgreSQL.

---

## Pré-requisitos

- [Node.js](https://nodejs.org/) v18+ (caso rode localmente sem Docker)
- [Yarn](https://yarnpkg.com/) ou [npm](https://www.npmjs.com/)
- [Docker](https://www.docker.com/) (opcional, recomendado)
- Banco de dados PostgreSQL (local ou em nuvem)

---

## Configuração do Ambiente

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/repo.git
   cd ic-scisci-backend/strapi
   ```

2. **Configure as variáveis de ambiente:**

   - Copie o arquivo `.env.example` para `.env` e ajuste conforme necessário:

     ```bash
     cp .env.example .env
     ```

   - Exemplo de variáveis importantes:
     ```
     DATABASE_CLIENT=postgres
     DATABASE_HOST=localhost
     DATABASE_PORT=5432
     DATABASE_NAME=postgres
     DATABASE_USERNAME=postgres
     DATABASE_PASSWORD=sua_senha
     DATABASE_SSL=false
     APP_KEYS=chave1,chave2
     ADMIN_JWT_SECRET=sua_chave_admin
     API_TOKEN_SALT=umSaltParaApiTokens
     TRANSFER_TOKEN_SALT=umSaltParaTransferencia
     JWT_SECRET=sua_jwt_secret
     ```

3. **Configure o banco de dados PostgreSQL:**

   - Certifique-se de que o banco está rodando e acessível com as credenciais acima.

---

## Rodando com Docker

1. **Suba o ambiente com Docker Compose:**

   ```bash
   docker-compose up
   ```

   Isso irá criar o container do Strapi e conectar ao banco PostgreSQL conforme configurado.

---

## Rodando Localmente (sem Docker)

1. **Instale as dependências:**

   ```bash
   yarn install
   # ou
   npm install
   ```

2. **Inicie o Strapi:**

   ```bash
   yarn develop
   # ou
   npm run develop
   ```

   O painel administrativo estará disponível em [http://localhost:1337/admin](http://localhost:1337/admin)

---

## Estrutura de Pastas

- `src/api/` — APIs customizadas e content-types do Strapi
- `src/admin/` — Customizações do painel administrativo
- `config/` — Configurações do Strapi (database, server, plugins, etc.)
- `public/` — Arquivos públicos e uploads
- `database/` — Migrations e arquivos do banco (se aplicável)

---

## Segurança

- Nunca compartilhe seu arquivo `.env` publicamente.
- Use tokens de API para autenticação entre frontend e backend.
- Altere as chaves secretas antes de subir para produção.

---

## Dicas

- Para acessar o painel admin, acesse `/admin` na porta configurada (padrão: 1337).
- Para gerar tokens de API, utilize o painel admin do Strapi.

---