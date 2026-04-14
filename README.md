# ReUse! — Plataforma Web

Plataforma de reutilização de itens usados, desenvolvida com **Next.js**, **Prisma ORM** e **PostgreSQL**.

## 📁 Estrutura do Projeto

```
nextjs-project/
├── app/
│   ├── layout.tsx          # Layout global (Header + Footer)
│   ├── globals.css         # Estilos globais
│   ├── page.tsx            # Página inicial (Hero + Produtos recentes)
│   ├── produtos/page.tsx   # Lista de produtos
│   ├── negociacao/page.tsx  # Negociações
│   ├── pedidos/page.tsx    # Meus pedidos
│   └── api/
│       ├── usuarios/route.ts    # CRUD de usuários
│       ├── produtos/route.ts    # CRUD de produtos
│       ├── negociacoes/route.ts # CRUD de negociações
│       └── pedidos/route.ts     # CRUD de pedidos
├── lib/
│   └── prisma.ts           # Instância do Prisma Client
├── prisma/
│   ├── schema.prisma       # Schema do banco de dados
│   └── seed.ts             # Dados iniciais (seed)
├── package.json
├── tsconfig.json
├── next.config.js
└── .env.example
```

## 🚀 Como Rodar

### 1. Instalar dependências
```bash
cd nextjs-project
npm install
```

### 2. Configurar banco de dados
Crie um arquivo `.env` baseado no `.env.example`:
```bash
cp .env.example .env
```
Edite com sua URL do PostgreSQL:
```
DATABASE_URL="postgresql://usuario:senha@localhost:5432/reuseweb"
```

### 3. Gerar Prisma Client e rodar migração
```bash
npx prisma generate
npx prisma migrate dev --name init
```

### 4. Popular o banco (seed)
```bash
npx tsx prisma/seed.ts
```

### 5. Iniciar o servidor
```bash
npm run dev
```
Acesse: http://localhost:3000

## 📊 Tabelas do Banco de Dados

| Tabela | Objetivo |
|--------|----------|
| **Usuario** | Armazena dados dos usuários (nome, email, senha) |
| **Produto** | Catálogo de itens disponíveis para troca/venda |
| **Negociacao** | Registro de negociações entre usuários |
| **Pedido** | Controle de pedidos realizados |

## 🔗 Endpoints da API

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| GET | /api/usuarios | Lista todos os usuários |
| POST | /api/usuarios | Cria novo usuário |
| GET | /api/produtos | Lista todos os produtos |
| POST | /api/produtos | Cria novo produto |
| GET | /api/negociacoes | Lista negociações |
| POST | /api/negociacoes | Cria nova negociação |
| GET | /api/pedidos | Lista pedidos |
| POST | /api/pedidos | Cria novo pedido |

## 🧪 Testando com curl

```bash
# Criar usuário
curl -X POST http://localhost:3000/api/usuarios \
  -H "Content-Type: application/json" \
  -d '{"nome":"Maria","email":"maria@example.com","senha":"123456"}'

# Listar usuários
curl http://localhost:3000/api/usuarios

# Criar produto
curl -X POST http://localhost:3000/api/produtos \
  -H "Content-Type: application/json" \
  -d '{"nome":"Violão","descricao":"Violão acústico","preco":300,"categoria":"Instrumentos","usuarioId":1}'

# Listar produtos
curl http://localhost:3000/api/produtos
```

## 🛠️ Tecnologias

- **Next.js 14** — Framework React com App Router
- **Prisma ORM** — Acesso tipado ao banco de dados
- **PostgreSQL** — Banco de dados relacional
- **TypeScript** — Tipagem estática
