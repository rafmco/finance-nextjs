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
  - [Shadcn DataTable](https://ui.shadcn.com/docs/components/data-table)
    - `npx shadcn@2.1.3 add table`
    - `npm install @tanstack/react-table@8.20.5`
    - Criar componente '/app/_components/ui/data-table.tsx'
    - *Criar componente 'columns.tsx' para cada utilização
  - `npx shadcn@2.1.3 add badge`
  - `npx shadcn@2.1.3 add dialog`
  - `npx shadcn@2.1.3 add form`
    - Instala automaticamente as libs [React Hook Form](https://www.react-hook-form.com) e [Zod](https://zod.dev)
    - Necessário criar um arquivo Zod Schema para cada uso
  - `npx shadcn@2.1.3 add select`
  - `npx shadcn@2.1.3 add input`
  - `npx shadcn@2.1.3 add popover`
  - `npx shadcn@2.1.3 add calendar`
    - Create a [Date Picker](https://ui.shadcn.com/docs/components/date-picker) component
  - `npx shadcn@2.1.3 add card`
  - `npx shadcn@2.1.3 add chart`
  - `npx shadcn@2.1.3 add progress`
  - `npx shadcn@2.1.3 add scroll-area`
  - `npx shadcn@2.1.3 add tooltip`
  - `npx shadcn@2.1.3 add alert-dialog`
  - `npx shadcn@2.1.3 add sonner`

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
  - '/.husk/pre-commit'
    - `npx lint-staged`
  - '/.lintstagedrc.json'
    - `{"*.ts?(x)": ["eslint --fix", "prettier --write"]}`

- Configurar padronização das mensagens de commit (compatível com Conventional Commits):
  - [git-commit-msg-linter](https://www.npmjs.com/package/git-commit-msg-linter)
  - `npm i git-commit-msg-linter@5.0.8`
  - '/.husk/commit-msg' >> `.git/hooks/commit-msg \$1`

- Instalar lib Prisma Client 5.21.1
  - `npm install @prisma/client@5.21.1`
  - Configurar '\app\_lib\prisma.ts' para não instanciar mais de um Prisma Client em Dev.

- Instalar lib React Number Format 5.4.2
  - `npm install react-number-format@5.4.2`

- Transformar '/app/page.tsx' em um `Route Group`
  - '/app/(home)/page.tsx'
  - '/app/(home)/_components/...tsx'
 
- Criar conta [Stripe](https://stripe.com)
  - Catálogo de Produtos
    - Adicionar Produto
      - Finance AI: Plano Premium
      - Mensal
    - Copiar Product_ID para adicionar ao .env:
      - `STRIPE_PREMIUM_PLAN_PRICE_ID=Product_ID`
  - Home
    - Copiar para adicionar ao .env:
      - `STRIPE_SECRET_KEY=Secret_Key`
      - `NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=Publishable_Key`
- Instalar lib [Stripe 17.3.1](https://www.npmjs.com/package/stripe)
  - `npm install stripe@17.3.1`
- Instalar lib [Stripe.JS 4.9.0](https://www.npmjs.com/package/@stripe/stripe-js?activeTab=versions)
  - `npm install @stripe/stripe-js@4.9.0`

- Configurar WebHooks no Stripe para Atualizar o Clerk ao confirmar Pagamento
  - [Destinos de Eventos](https://dashboard.stripe.com/test/workbench/webhooks)
  - Teste com um ouvinte local
  - Baixe a [Stripe CLI](https://docs.stripe.com/stripe-cli?install-method=docker) (Docker)
    - `docker run --rm --entrypoint /bin/sh -it stripe/stripe-cli:latest`
    - `[stripe login](https://github.com/stripe/stripe-cli/issues/497#issuecomment-686558554)`
    - Conceda acesso acessando link fornecido e o app de autenticação
  - Encaminhe eventos ao seu destino
    - `stripe listen --forward-to localhost:3000/api/webhooks/stripe`
    - Adicione a chave gerada ao .env
      - `STRIPE_WEBHOOK_SECRET="Webhook_Secret"`
    - Configurações -> Faturamento -> [Portal do Cliente](https://dashboard.stripe.com/test/settings/billing/portal)
      - Ativar Link de Teste
        - Adicione ao .env
          - `NEXT_PUBLIC_STRIPE_CUSTOMER_PORTAL_URL="Customer_Portal"`
  - Acione eventos com a CLI
    - `stripe trigger payment_intent.succeeded`
   
- Criar conta [OPEN AI](https://platform.openai.com/docs/overview)
  - `OPENAI_API_KEY="AI_KEY"`
- Instalar lib [Open AI](https://www.npmjs.com/package/openai)
  - `npm i openai@4.71.1`
 
- Instalar lib [react-markdown](https://www.npmjs.com/package/react-markdown)
  - `npm i react-markdown@9.0.1`
 
- Instalar lib [@tailwindcss/typography](https://www.npmjs.com/package/@tailwindcss/typography)
  - `npm install -D @tailwindcss/typography@0.5.15`

- Para Deploy:
  - Package.json
    - `"prepare": "husky && prisma generate"`
  - .env
    - `APP_URL="http://localhost:3000"`
