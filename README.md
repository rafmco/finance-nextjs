<a name="readme-top"></a>

  <h1 align="center">finance-nextjs</h1>
<p align="center">
</p>

## 🙋 Autor

👋 Olá, Sou Rafael Machado.

🚀 Redes:

- [LinkedIn](https://www.linkedin.com/in/rafmco/)

## 📊 Controle Financeiro - App FullStack em NEXTJS e REACTJS

Uma plataforma web para para otimizar o seu controle financeiro, seus recebimentos, gastos e investimentos.
Gerencie suas transações com uma interface intuitiva, transforma a gestão de seu dinheiro em uma experiência ágil e descomplicada.
Tenhas insights gerados por Inteligência Artificial que lhe ajudarão a gerir melhor seu futuro.

## 🛠️ Construído com:

- [![NextJS][Next.js]][Next-url]
- [![ReactJS][React.js]][React-url]
- [![TypeScript][TypeScript]][TypeScript-url]
- [![NPM][NPM]][NPM-url]
- PRISMA
- MYSQL
- CLERK
- STRIPE

## 🚀 Instalação

1. Baixe o repositório (`git clone git@github.com:Rafmco/finance-nextjs.git`)
2. Navegue até a pasta do projeto (`cd finance-nextjs`)
3. Instalar dependências `npm install`
4. Copie `.env.example` para `.env.local` e altere os valores das variáveis de ambiente
5. `npm run dev`
6. Abrir `http://localhost:3000`

## 💻 Requisitos

- Windows
  - Node.js

## 💻 Extensões recomendadas para VS Code:

- [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Simple React Snippets](https://marketplace.visualstudio.com/items?itemName=burkeholland.simple-react-snippets)
- [Color Highlight](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)
- [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)

- Configurar no VS Code:
  - Setttings -> Editor: Default Formatter = Prettier
  - Setttings -> Editor: Format On Save [x]

## 🚶‍♂️ Etapas

- Criar Projeto
  - `npx create-next-app@latest barber-fullstack`
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

## 📔 Contribuindo

Para contribuir para este projeto, siga as [Normas de Commit](CONTRIBUTING.md).

<!-- - Configurar cores no globals.css -->
<!-- - Add Docker-compose.yml -->

## 📚 Referências

- 🔗 [FullStackBarber](https://github.com/rafmco/fullstack-barber)

## © Licença

Distribuído sob a licença MIT. Veja `LICENSE.txt` para mais informações.

<p align="right">(<a href="#readme-top">Voltar ao inicio</a>)</p>

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[forks-shield]: https://img.shields.io/github/forks/freitas-miranda/login-nest.svg?style=for-the-badge
[forks-url]: https://github.com/freitas-miranda/login-nest/network/members
[stars-shield]: https://img.shields.io/github/stars/freitas-miranda/login-nest.svg?style=for-the-badge
[stars-url]: https://github.com/freitas-miranda/login-nest/stargazers
[issues-shield]: https://img.shields.io/github/issues/freitas-miranda/login-nest.svg?style=for-the-badge
[issues-url]: https://github.com/freitas-miranda/login-nest/issues
[license-shield]: https://img.shields.io/github/license/freitas-miranda/login-nest.svg?style=for-the-badge
[license-url]: https://github.com/freitas-miranda/login-nest/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/freitas-miranda
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[NextAuth]: https://img.shields.io/badge/next--auth-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[NextAuth-url]: https://authjs.dev/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[React Native]: https://img.shields.io/badge/react_native-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB
[React Native-url]: https://reactnative.dev/
[Node.js]: https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white
[Node-url]: https://nodejs.org/pt-br
[Yarn]: https://img.shields.io/badge/yarn-%232C8EBB.svg?style=for-the-badge&logo=yarn&logoColor=white
[Yarn-url]: https://yarnpkg.com/
[Jest]: https://img.shields.io/badge/-jest-%23C21325?style=for-the-badge&logo=jest&logoColor=white
[Jest-url]: https://jestjs.io/pt-BR/
[Git]: https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white
[Git-url]: https://git-scm.com/
[GitHub]: https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white
[GitHub-url]: https://github.com/
[GitHubActions]: https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white
[GitHubActions-url]: https://github.com/features/actions
[GoogleAPI]: https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white
[GoogleAPI-url]: https://console.cloud.google.com
[MariaDB]: https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white
[MariaDB-url]: https://mariadb.org/
[Fastify]: https://img.shields.io/badge/fastify-%23000000.svg?style=for-the-badge&logo=fastify&logoColor=white
[Fastify-url]: https://fastify.dev/
[NestJS]: https://img.shields.io/badge/nestjs-%23E0234E.svg?style=for-the-badge&logo=nestjs&logoColor=white
[NestJS-url]: https://nestjs.com/
[RabbitMQ]: https://img.shields.io/badge/Rabbitmq-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white
[RabbitMQ-url]: https://www.rabbitmq.com/
[AWS]: https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white
[AWS-url]: https://aws.amazon.com/pt/
[TypeScript]: https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white
[TypeScript-url]: https://www.typescriptlang.org/
[Docker]: https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white
[Docker-url]: https://www.docker.com/
[Notion]: https://img.shields.io/badge/Notion-%23000000.svg?style=for-the-badge&logo=notion&logoColor=white
[Notion-url]: https://www.notion.so/
[Expo]: https://img.shields.io/badge/Build-3275E7.svg?style=for-the-badge&logo=EXPO&labelColor=000&logoColor=FFF
[Expo-url]: https://expo.dev
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Vuetify]: https://img.shields.io/badge/Vuetify-1867C0?style=for-the-badge&logo=vuetify&logoColor=AEDDFF
[Vuetify-url]: https://vuetifyjs.com/en/
[Express]: https://img.shields.io/badge/Express.js-404D59?style=for-the-badge
[Express-url]: https://github.com/expressjs/express
[MongoDB]: https://img.shields.io/badge/MongoDB-4EA94B?logo=mongodb&logoColor=white&style=for-the-badge
[MongoDB-url]: https://www.mongodb.com
[Socket.io]: https://img.shields.io/badge/Socket.io-black?style=for-the-badge&logo=socket.io&badgeColor=010101
[Socket.io-url]: https://socket.io
[Vite]: https://img.shields.io/badge/vite-%23646CFF.svg?style=for-the-badge&logo=vite&logoColor=white
[Vite-url]: https://vitejs.dev
[SolidJS]: https://img.shields.io/badge/SolidJS-2c4f7c?style=for-the-badge&logo=solid&logoColor=c8c9cb
[SolidJS-url]: https://www.solidjs.com
[NPM]: https://img.shields.io/badge/NPM-%23CB3837.svg?style=for-the-badge&logo=npm&logoColor=white
[NPM-url]: https://www.npmjs.com
