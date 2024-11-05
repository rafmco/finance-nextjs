# Guia de Desenvolvimento

## ❗ Etapas

- Criar Projeto
  \*/NextJS 15 é a Versão atual que usa React 19

* Mas devido o React 19 não estar oficialmente estável
* Vamos usar NextJS 14:\*/

- `npx create-next-app@14.2.16`
  ? Project named » finance-nextjs
  ? TypeScript? » Yes
  ? ESLint? » Yes
  ? Tailwind CSS? » Yes
  ? `src/` directory? » No
  ? App Router? » Yes
  ? import alias (@/\*)? » No

- Add .env (.env.local e .env.example)
- Add lib Shadcn/ui
  - `npx shadcn-ui@latest init`
- Alteração da estrutura de pastas padrão de componentes Shadcn (components.json):
  - `@/app/_components`
  - `@/app/_lib/utils`
- Instalação dos componentes Shadcn:
  - `npx shadcn-ui@latest add button`
  - `npx shadcn-ui@latest add card`
  - `npx shadcn-ui@latest add sheet`
  - `npx shadcn-ui@latest add avatar`
  - `npx shadcn-ui@latest add input`
  - `npx shadcn-ui@latest add alert-dialog`
  - `npx shadcn-ui@latest add sonner`
- Instalar [Automatic Class Order para Tailwind](https://tailwindcss.com/blog/automatic-class-sorting-with-prettier)
  - `npm install -D prettier prettier-plugin-tailwindcss`
  - Add `.prettierrc` (arquivo de configuração do Prettier)
- Configurar Git Hooks com [Husky](https://www.npmjs.com/package/husky) (rodar eslint nos arquivos alterados antes de commits):
  - `npm install -D husky lint-staged`
  - `npx husky init`
  - .husk/pre-commit `npx lint-staged`
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
