<!-- Brief principal: -->
<!-- Serviços visuais verificados antes da composição: Readme Typing SVG, GitHub Profile Summary Cards, GitHub Streak Stats, Platane/snk, Skill Icons e Shields.io. -->

<div align="center">

# William Silva

### Full Stack Developer

<img
  src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=22&pause=1200&color=58A6FF&center=true&vCenter=true&width=650&lines=Full+Stack+Developer;SaaS+%26+Web+Applications;Backend+%26+Web+Development;TypeScript+%2F+React+%2F+Next.js;Supabase+%2F+PostgreSQL"
  alt="Typing SVG"
/>

**Santa Catarina, Brasil**

<a href="https://github.com/NodeWillDev">
  <img src="https://img.shields.io/badge/GitHub-NodeWillDev-181717?style=flat-square&logo=github" alt="GitHub">
</a>
<a href="https://nodewilldev.github.io/my-portfolio/">
  <img src="https://img.shields.io/badge/Portfolio-nodewilldev-0A66C2?style=flat-square&logo=vercel&logoColor=white" alt="Portfolio">
</a>
<a href="https://www.linkedin.com/in/william-silva-7b9381248/">
  <img src="https://img.shields.io/badge/LinkedIn-William%20Silva-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn">
</a>

</div>

---

## Sobre

Desenvolvo **aplicações web e sistemas SaaS ponta a ponta**, trabalhando desde a interface e experiência de uso até APIs, modelagem de banco, autenticação, autorização e regras de negócio.

Meu foco atual está em aplicações construídas com **TypeScript, React, Next.js, Node.js, Supabase e PostgreSQL**, especialmente sistemas que envolvem múltiplos usuários, isolamento de dados, controle de acesso e processos operacionais reais.

Um dos principais contextos em que venho trabalhando é um **SaaS multiempresa para estabelecimentos do setor de alimentação**, envolvendo mesas, sessões, pedidos, QR Codes, colaboradores, estoque, autenticação e regras de autorização no backend e no banco de dados.

---

## Stack principal

<div align="center">

<a href="https://skillicons.dev">
  <img src="https://skillicons.dev/icons?i=ts,js,react,nextjs,nodejs,tailwind,supabase,postgres,git,github,vercel&theme=dark&perline=11" alt="Main Stack">
</a>

</div>

<br>

<table>
<tr>
<td width="25%" valign="top">

### Frontend

`TypeScript`  
`JavaScript`  
`React`  
`Next.js`  
`Tailwind CSS`  
`SWR`  
`Font Awesome`

</td>
<td width="25%" valign="top">

### Backend

`Node.js`  
`Next.js`  
`TypeScript`  
`REST APIs`  
`External APIs`  
`JWT`

</td>
<td width="25%" valign="top">

### Data

`PostgreSQL`  
`Supabase`  
`SQL`  
`JSON / JSONB`  
`RPCs`  
`Row Level Security`

</td>
<td width="25%" valign="top">

### Infrastructure

`Git`  
`GitHub`  
`Vercel`  
`Supabase`

</td>
</tr>
</table>

### Experiência adicional

`MySQL` · `Prisma` · `TypeORM` · `Electron` · `PocketMine-MP`

Essas tecnologias fazem parte de projetos ou experiências específicas e não representam necessariamente minha stack principal atual.

---

## O tipo de software que venho construindo

<table>
<tr>
<td width="50%" valign="top">

### Backend & APIs

APIs, integrações externas e lógica de negócio utilizando principalmente **Node.js, TypeScript e Next.js**.

Trabalho com validação de recursos, persistência, relacionamentos, estados de aplicação e regras que precisam continuar consistentes entre frontend, backend e banco.

</td>
<td width="50%" valign="top">

### SaaS & Multi-tenant

Estruturas onde diferentes empresas compartilham a mesma aplicação mantendo **contexto, histórico, usuários e dados isolados**.

Isso inclui decisões envolvendo `company_id`, controle de acesso por empresa, integridade e escalabilidade da modelagem.

</td>
</tr>
<tr>
<td width="50%" valign="top">

### Authentication & Security

Experiência com **Supabase Auth, JWT, access tokens, claims, roles, sessões, permissões e Row Level Security**.

O objetivo é definir não apenas quem está autenticado, mas **qual recurso cada usuário realmente pode acessar**.

</td>
<td width="50%" valign="top">

### Database Design

Modelagem relacional com **PostgreSQL e Supabase**, trabalhando com relacionamentos, UUIDs, identity columns, enums, constraints, índices, timestamps, JSONB e RPCs.

Parte das regras de negócio também pode ser executada diretamente no banco quando isso melhora consistência e segurança.

</td>
</tr>
</table>

---

# Projeto principal

## Restaurante Online

<img src="https://img.shields.io/badge/status-em%20desenvolvimento-238636?style=flat-square" alt="Em desenvolvimento">
<img src="https://img.shields.io/badge/modelo-SaaS-1F6FEB?style=flat-square" alt="SaaS">
<img src="https://img.shields.io/badge/arquitetura-multiempresa-8957E5?style=flat-square" alt="Multiempresa">

SaaS em desenvolvimento para **restaurantes, hamburguerias, pizzarias, lanchonetes, bares, cafeterias, padarias, operações de delivery próprio e outros estabelecimentos do setor de alimentação**.

O sistema foi pensado para centralizar processos que normalmente ficam espalhados entre comandas, atendimento manual, controle de mesas, pedidos, estoque e ferramentas separadas.

### O que o sistema trabalha

- Gestão de **mesas, sessões e pedidos**
- Identificação de quem realizou cada pedido
- Histórico de pedidos e consumo
- Produtos, cardápios, quantidades e status
- Controle operacional e estoque
- Colaboradores e permissões
- Autenticação e contexto de empresa
- Operação **multiempresa**
- Acesso por **QR Codes físicos**
- Entrada de clientes e funcionários em sessões existentes
- Usuários autenticados e anônimos

### Uma das partes mais interessantes da arquitetura

O QR Code de uma mesa é físico e permanente, mas a autorização para utilizá-lo não pode ser.

Por isso, o fluxo precisa considerar:

`QR Code` → `Mesa` → `Sessão ativa` → `Usuário` → `Permissão` → `Pedido`

Isso envolve situações como clientes que saem e retornam, funcionários entrando em sessões existentes, sessões canceladas, acessos indevidos e usuários anônimos que não devem permanecer indefinidamente no sistema.

Parte dessas validações foi levada para **RPCs e regras no banco**, incluindo:

- validação de existência de mesas;
- validação e cancelamento de sessões;
- limpeza de usuários anônimos;
- retorno estruturado de erros;
- agregação de pedidos utilizando `JSONB`;
- associação entre pedido e usuário responsável;
- regras de autorização e controle de acesso.

### Stack

`Next.js` · `React` · `TypeScript` · `Tailwind CSS` · `Supabase` · `PostgreSQL` · `SWR` · `Vercel` · `Font Awesome`

---

## Projetos selecionados

| Projeto | O que foi construído | Tecnologias / conceitos |
|---|---|---|
| **[minecraft-auth-registry](https://github.com/NodeWillDev/minecraft-auth-registry)** | Sistema de autenticação e registro de usuários integrado a servidores Minecraft. | `TypeScript` `Node.js` `TypeORM` `MySQL` `APIs` `PocketMine-MP` |
| **[shopping-cart](https://github.com/NodeWillDev/shopping-cart)** | Aplicação web de carrinho de compras com persistência de dados. | `Next.js` `TypeScript` `Prisma` `MySQL` |
| **[chat-realtime](https://github.com/NodeWillDev/chat-realtime)** | Projeto voltado a comunicação em tempo real e separação entre frontend e backend. | `TypeScript` `APIs` `Realtime` `Frontend / Backend` |
| **[minecraft-ban-registry](https://github.com/NodeWillDev/minecraft-ban-registry)** | Sistema para registrar e consultar histórico de banimentos em servidores Minecraft. | `TypeScript` `Backend` `APIs` `PocketMine-MP` |
| **[bitcoin-monitoring](https://github.com/NodeWillDev/bitcoin-monitoring)** | Experimento desktop para monitoramento de Bitcoin consumindo dados externos. | `Node.js` `Electron` `CoinMarketCap API` |

<sub>O projeto <strong>bitcoin-monitoring</strong> é experimental e não foi concluído.</sub>

---

## Backend, banco e regras de negócio

Grande parte do meu trabalho não está apenas em criar telas ou endpoints isolados, mas em definir como os dados e as regras do sistema se relacionam.

```text
Application
│
├── Authentication
│   ├── Users
│   ├── Sessions
│   ├── Tokens
│   ├── Roles
│   └── Claims
│
├── Authorization
│   ├── Permissions
│   ├── Company context
│   ├── Resource validation
│   └── Row Level Security
│
├── Business Logic
│   ├── APIs
│   ├── RPCs
│   ├── State transitions
│   └── Operational rules
│
└── Data
    ├── PostgreSQL
    ├── Relational modeling
    ├── Constraints
    ├── Indexes
    ├── JSONB
    └── Data integrity
```

### Banco de dados

Tenho experiência prática trabalhando com:

`PostgreSQL` · `Supabase Database` · `MySQL` · `SQL` · `Prisma` · `TypeORM`

e com conceitos como:

`UUID` · `Identity columns` · `Enums` · `Constraints` · `Relationships` · `Indexes` · `Timestamps` · `JSONB` · `RPCs` · `RLS`

### Segurança e autorização

Também trabalho com:

`Supabase Auth` · `JWT` · `Access Tokens` · `Claims` · `Roles` · `Sessions` · `Permissions` · `Route Security` · `Row Level Security`

Em sistemas multiempresa, isso inclui garantir que a autenticação de um usuário não seja confundida com autorização para acessar recursos pertencentes a outra empresa.

---

## GitHub

<div align="center">

<img
  width="100%"
  src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=NodeWillDev&theme=github_dark&animation=load"
  alt="GitHub Profile Details"
/>

<br><br>

<img
  width="49%"
  src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=NodeWillDev&theme=github_dark&animation=load"
  alt="GitHub Stats"
/>
<img
  width="49%"
  src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=NodeWillDev&theme=github_dark&animation=load"
  alt="Languages by Repository"
/>

<br><br>

<img
  src="https://streak-stats.demolab.com/?user=NodeWillDev&theme=dark&hide_border=true&locale=pt_BR"
  alt="GitHub Streak"
/>

</div>

---

## Contributions

<div align="center">

<img
  src="https://raw.githubusercontent.com/NodeWillDev/NodeWillDev/output/github-contribution-grid-snake-dark.svg"
  alt="GitHub Contribution Snake"
/>

</div>

---

## Onde meu trabalho se concentra

<div align="center">

`Full Stack Development`
&nbsp;•&nbsp;
`Backend Development`
&nbsp;•&nbsp;
`SaaS`
&nbsp;•&nbsp;
`Web Applications`

`Software Architecture`
&nbsp;•&nbsp;
`Database Design`
&nbsp;•&nbsp;
`APIs`
&nbsp;•&nbsp;
`Authentication`

`Authorization`
&nbsp;•&nbsp;
`Application Security`
&nbsp;•&nbsp;
`Business Logic`
&nbsp;•&nbsp;
`Multi-tenant Applications`

`UI/UX`
&nbsp;•&nbsp;
`Performance`
&nbsp;•&nbsp;
`Cloud Deployment`

</div>

---

## Links

<div align="center">

<a href="https://github.com/NodeWillDev">
  <img src="https://img.shields.io/badge/GitHub-NodeWillDev-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
</a>
<a href="https://nodewilldev.github.io/my-portfolio/">
  <img src="https://img.shields.io/badge/Portfolio-Visit-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio">
</a>
<a href="https://www.linkedin.com/in/william-silva-7b9381248/">
  <img src="https://img.shields.io/badge/LinkedIn-William%20Silva-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
</a>
<a href="https://www.instagram.com/_is_william/">
  <img src="https://img.shields.io/badge/Instagram-_is__william-E4405F?style=for-the-badge&logo=instagram&logoColor=white" alt="Instagram">
</a>
<a href="mailto:williamdasilva.dev@gmail.com">
  <img src="https://img.shields.io/badge/E--mail-williamdasilva.dev%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email">
</a>

</div>

<br>

<div align="center">
  <sub>William Silva · NodeWillDev · Full Stack Developer</sub>
</div>
