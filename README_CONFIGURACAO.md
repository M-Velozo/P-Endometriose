# Instruções para Configuração e Execução Local - Projeto P-Médico

Este documento detalha os passos necessários para configurar e executar o projeto P-Médico em um ambiente de desenvolvimento local.

## Pré-requisitos

- **Node.js**: Versão 20 ou superior
- **npm**: Gerenciador de pacotes do Node.js

## 1. Instalação de Dependências

Navegue até o diretório raiz do projeto e execute o seguinte comando para instalar todas as dependências necessárias:

```bash
npm install
```

## 2. Configuração do Ambiente

Crie um arquivo `.env` na raiz do projeto com o seguinte conteúdo:

```env
# Database
DATABASE_URL="file:./db/custom.db"

# Next.js
NODE_ENV=development
NEXTAUTH_SECRET=your-secret-key-here
NEXTAUTH_URL=http://localhost:3000

# Application
PORT=3000
HOST=0.0.0.0
```

## 3. Configuração do Banco de Dados

Execute os seguintes comandos para gerar o cliente Prisma e aplicar o schema do banco de dados:

```bash
npm run db:generate
npm run db:push
```

Para popular o banco de dados com dados de exemplo, inicie o servidor (passo 4) e execute o seguinte comando em um novo terminal:

```bash
curl -X POST http://localhost:3000/api/seed
```

## 4. Execução do Servidor

Para iniciar o servidor de desenvolvimento, execute o comando:

```bash
npm run dev
```

O servidor estará disponível em `http://localhost:3000`.

## 5. Acesso à Aplicação

Abra seu navegador e acesse `http://localhost:3000` para visualizar a aplicação em funcionamento.

## Scripts Úteis

- `npm run build`: Compila a aplicação para produção.
- `npm run start`: Inicia o servidor em modo de produção.
- `npm run lint`: Executa o linter para análise de código.
- `npm run db:migrate`: Executa as migrações do banco de dados.
- `npm run db:reset`: Reseta o banco de dados.

