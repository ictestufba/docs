# Instruções para implantação do projeto

Para implantação do projeto, é necessário rodar o back-end (API) e o front-end, conforme instruções a seguir.

## Configuração necessária

- Docker
- Node.js (versão LTS atualizada), com NPM

## Back-end

- Com o Docker e o Node.js instalado, clone o repositório o [repositório do back-end](https://github.com/ictestufba/ictest-backend).

- Na raiz do projeto, crie um arquivo `.env` para declarar as variáveis de ambiente `NODE_ENV`, `JWT_SECRET` e `DATABASE_URL` (veja o exemplo no arquivo `.env.example`). Dica do formato da URL do PostgreSQL: `postgresql://usuario:senha@ip:porta/banco-de-dados?schema=nome-do-schema`. Para o caso do ambiente de desenvolvimento, conforme o docker-compose: `postgresql://docker:docker@localhost:5432/ictest?schema=public`

- Dentro da pasta do projeto, rode os comandos a seguir para subir o banco de dados e instalar as dependências:

```bash
docker compose up -d
```

```bash
npm i
```

- Com as dependências instaladas e com o banco de dados rodando, execute o comando a seguir para subir as migrações:

```bash
npx prisma migrate dev
```

- Rode o comando a seguir para gerar uma versão de produção do projeto:

```bash
npm run build
```

- Por fim, rode o back-end com o seguinte comando:

```bash
npm run start
```

## Front-end

- Com o Docker e o Node.js instalado, clone o repositório o [repositório do front-end](https://github.com/ictestufba/ictest-frontend).

- Dentro da pasta do projeto, rode o comando a seguir para instalar as dependências:

```bash
npm i
```

- Na raiz do projeto, crie um arquivo `.env` para declarar a variável de ambiente `NEXT_PUBLIC_API_URL` (veja o exemplo no arquivo `.env.example`). Trabalhando com a API local esse valor será `http://localhost:8080`.

- Gere uma versão de produção do front-end com o comando a seguir:

```bash
npm run build
```

- Para rodar o front-end, execute o seguinte comando:

```bash
npm run start
```

- Para acessar a aplicação, abra algum navegador no endereço `http://localhost:3000/login`

# Documentação

## Ferramenta de gestão
GitHub Projects (issues e milestones)

## Processo de desenvolvimento
Kanban

## Requisitos
[Documento de requisitos](https://docs.google.com/spreadsheets/d/1_8DkqfZRIkV0UVfI4jnyzxO-GWy2yUjhO6l257PduEU/edit#gid=0)

## Tecnologias

## Design
- Figma
- Whimsical

## Frontend
- React
- Biblioteca de UI (1): [Ant Design](https://ant.design/components/overview/)
- Testes unitários: jest + react test library
- Testes E2E: Playwright ou Cypress

## Backend
- Runtime: NodeJS
- Framework: Express
- Banco de dados: MongoDB (Mongoose como ODM)
- Testes unitários: jest

## Documentos complementares

**[🖼️ Apresentação](https://docs.google.com/presentation/d/1up1pNUc-lEF3kwGWe2mHribKED30_BXIN3M7yvZcyCs/edit?usp=sharing)**

**[📝Requisitos](https://docs.google.com/spreadsheets/d/1_8DkqfZRIkV0UVfI4jnyzxO-GWy2yUjhO6l257PduEU/edit#gid=0)**

**[🏽‍💻 Organização](https://github.com/ictestufba)**

**[🛠️Projeto](https://github.com/orgs/ictestufba/projects/1)**

**[🔀 ERD](https://whimsical.com/erd-ictest-7T2iPXGwiC9E3aRY5in5Uq)**

**[🎨 Protótipo Navegável](https://www.figma.com/proto/eRpAMntIiMcvAIUacHEoez/ictestufba?node-id=57-16051&scaling=min-zoom&page-id=1%3A2&starting-point-node-id=57%3A16051)**

**[➡️UserFlow](https://whimsical.com/userflow-ictest-XxSCN4xxVWwnpLDXXVJY7F)**

**[📐Arquitetura](https://whimsical.com/ictest-arquitetura-82rUC9BaZGkek2YkNim7E9)**

**[💻 Aplicação em produção](https://ictest-frontend.vercel.app/login)**

**[🧪Apresentação - Testes](https://docs.google.com/presentation/d/102RCn6x8P_sTnGRlzhLy_tyw5474Rn4yu79ui5ljgCk/edit?usp=sharing)**
