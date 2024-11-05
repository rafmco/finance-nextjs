# Guia de Desenvolvimento

## ❗ Etapas

- Criar Projeto:
  - NextJS 15 é a Versão atual que usa React 19, mas devido o React 19 não estar oficialmente estável vamos usar NextJS 14:    
  - `npx create-next-app@14.2.16`
  - `? Project named » finance-nextjs`
  - `? TypeScript? » Yes`
  - `? ESLint? » Yes`
  - `? Tailwind CSS? » Yes`
  - `? src/ directory? » No`
  - `? App Router? » Yes`
  - `? import alias (@/\*)? » No`

- Add .env e .env.example:
  - `DATABASE_URL="mysql://root:password@localhost:3306/finance"`

- Add lib Prisma 5.21.1
  - `npm install prisma@5.21.1`
  - `npx prisma init`

- Configurar Tabelas em prisma/schema.prisma

- Criar manualmente o Schema no Banco destino

- Criar migration
  - `npx prisma migrate dev --name init_db`

- Add plugin [Prettier Tailwind](https://github.com/tailwindlabs/prettier-plugin-tailwindcss)
  - `npm install -D prettier prettier-plugin-tailwindcss`
  - Add arquivo .prettierrc.json

- Add lib Shadcn/ui 2.1.3
  - `npx shadcn@2.1.3 init`
  - `? Style » Default`
  - `? Base Color » Neutral`
  - `? Css Variables » Yes`

- Alteração da estrutura de pastas padrão de componentes Shadcn:
  - Mover '/lib' para '/app'
  - Renomear para '/_lib' (pasta privada)
  - `@/app/_lib/utils`
  - Alterar 'aliases' em '/components.json'
  - `@/app/_components`
  - `@/app/_lib/utils`
  - `@/app/_components/ui`
  - `@/app/_lib`
  - `@/app/_hooks`
  
- Instalação dos componentes Shadcn:
  - `npx shadcn@2.1.3 add button`

  - `npx shadcn-ui@latest add card`
  - `npx shadcn-ui@latest add sheet`
  - `npx shadcn-ui@latest add avatar`
  - `npx shadcn-ui@latest add input`
  - `npx shadcn-ui@latest add alert-dialog`
  - `npx shadcn-ui@latest add sonner`
 
- Criar conta [Clerk](https://clerk.com)
  - Cadastrar Aplicação
  - Permitir Sign In por Email e Google
- Instalar lib Clerk
  - `npm install @clerk/nextjs@5.7.5`
  - Definir variáveis de ambiente
  - Criar arquivo /middleware.ts
  - Add ClerkProvider to '/app/layout.tsx'
- Instalar Clerk Themes
  - `npm install @clerk/themes@2.1.37`

- Configurar Git Hooks com [Husky](https://www.npmjs.com/package/husky) (rodar eslint nos arquivos alterados antes de commits):
  - `npm install -D husky@9.1.6`
  - `npm install -D lint-staged@12.3.2`
  - `npx husky init`
  - .husk/pre-commit >> `npx lint-staged`
  - .lintstagedrc.json `{"*.ts?(x)": ["eslint --fix", "prettier --write"]}`

- Configurar regras do ESlint:
  - `.eslintrc.json`

- Configurar padronização das mensagens de commit (compatível com Conventional Commits):
  - [git-commit-msg-linter](https://www.npmjs.com/package/git-commit-msg-linter)
  - Work with Husky 5 -> configurar .husk/commit-msg

- Instalar Redux:
  - `npm install @reduxjs/toolkit react-redux redux-persist`

- Instalar Zod:
  - `npm install --save-dev zod-prisma-types`
