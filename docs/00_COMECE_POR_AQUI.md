# 00_INICIAR_POR_AQUI: O Playbook Definitivo de Engenharia de Software

Este é o momento em que a engenharia de software deixa de ser apenas "escrever código" e passa a ser **construção de produtos escaláveis**. 

Para utilizar os prompts de Elite que criamos (Segurança, Escalabilidade, Testes e Backend) em conjunto com as Skills do seu ambiente (Antigravity), você precisa de um **Framework de Trabalho (Workflow)**.

Abaixo, apresento o mapa de desenvolvimento definitivo, estruturado cronologicamente.

---

## Fase 0: O Ponto de Partida (Setup Físico)
Tudo começa no sistema operacional e no seu ambiente de desenvolvimento (Antigravity).

1. **Criar a pasta do projeto:** 
   ```bash
   mkdir meu-projeto-escalavel && cd meu-projeto-escalavel
   ```
2. **Abrir no Antigravity:** Iniciar a IDE/Workspace.
3. **O Passo Oculto (Git):** Antes de qualquer arquivo, inicialize o versionamento: 
   ```bash
   git init
   ```
4. **Estrutura Base de Documentação:** Crie uma pasta chamada `/docs`. É aqui que a mágica da engenharia começa.

---

## Fase 1: O Plano do Projeto (Project Plan)
* **Quando criar:** É o **primeiro** documento. Antes de pensar em código, banco de dados ou telas.
* **Finalidade/Objetivo:** Definir o **"Por quê?"** e o **"Quando?"**. Ele alinha a visão de negócios. Responde se o projeto vale a pena ser feito, qual o orçamento, o prazo e quem são os envolvidos.
* **O que contém:** Visão geral, objetivos de negócio, KPIs de sucesso, cronograma macro e restrições.
* **Como usar a IA:** Ative a skill `project-planner.md` ou `product-manager.md` e peça: *"Crie um Plano de Projeto para um sistema de [sua ideia]."*

---

## Fase 2: O PRD (Product Requirements Document)
* **Quando criar:** Imediatamente após o Plano do Projeto ser aprovado.
* **Finalidade/Objetivo:** Definir o **"O quê?"**. Ele traduz a visão de negócios em funcionalidades reais. É o contrato do que será construído.
* **O que contém:** Personas (quem vai usar), Histórias de Usuário (User Stories), Critérios de Aceite, Escopo do MVP (Produto Mínimo Viável) e Requisitos Não-Funcionais (ex: "O sistema deve suportar 10.000 usuários").
* **Como usar a IA:** Ative a skill `product-owner.md` e peça: *"Com base no Plano de Projeto, redija o PRD detalhando as histórias de usuário e o escopo do MVP."*

---

## Fase 3: As SPECs (Especificações Técnicas)
* **Quando criar:** Somente após o PRD estar "congelado" (fechado). Não se projeta arquitetura sem saber o que o sistema vai fazer.
* **Finalidade/Objetivo:** Definir o **"Como?"**. É aqui que os Engenheiros Sêniores entram. Este documento traduz as funcionalidades do PRD em tecnologia pura.
* **O que contém:** Arquitetura do sistema, Diagrama de Banco de Dados (MER), Contratos de API (Swagger/OpenAPI), Stack Tecnológico e Fluxos de Autenticação.
* **Como usar a IA:** **É AQUI QUE USAMOS NOSSOS PROMPTS DE ELITE.**
  * Alimente a IA com o PRD e ative o **Prompt de Escalabilidade** + **Prompt de Segurança (Purple Team)**.
  * Peça: *"Atuando com as diretrizes de Escalabilidade e Segurança, crie a SPEC técnica para este PRD. Defina a arquitetura, o modelo de dados e a modelagem de ameaças."*

---

## Fase 4: O Que Mais Falta? (O "Pulo do Gato" Sênior)
Antes de começar a codar o backend, engenheiros de elite fazem mais três coisas:

1. **Modelagem de Ameaças (Threat Modeling):** Analisar a SPEC e perguntar: *"Como um hacker roubaria dados dessa arquitetura?"* (Use o prompt de Segurança aqui).
2. **Setup de Infraestrutura Local (Docker):** Criar o `docker-compose.yml` com o banco de dados, Redis e filas locais. (Use a skill `devops-engineer.md`).
3. **Definição de Linting e Padrões:** Configurar ESLint, Prettier, SonarQube ou Ruff (Python) para que o código já nasça padronizado.

---

## Fase 5: Execução e Testes (A Mão na Massa)
Com `/docs/plan.md`, `/docs/prd.md` e `/docs/specs.md` prontos, o desenvolvimento vira uma linha de montagem previsível:

1. **Codificação:** Use o nosso **Prompt de Backend/Scraping** para gerar o código seguindo a SPEC.
2. **Testes e Estresse:** Use o nosso **Prompt de SRE/QA Automation** para tentar quebrar o que acabou de ser construído.

---

## Como Documentar e Criar uma Rotina Profissional (O Playbook)

Para nunca mais começar um projeto do zero e garantir que você sempre siga esse padrão, você deve criar um **Template de Inicialização (Boilerplate)**.

Crie um repositório (ou uma pasta no seu computador) chamado `template-projeto-padrao`. Dentro dele, deixe a seguinte estrutura vazia, pronta para ser copiada:

```text
meu-projeto-padrao/
├── .gitignore
├── README.md
├── docs/
│   ├── 00_INICIAR_POR_AQUI.md (Este arquivo)
│   ├── 01_PROJECT_PLAN.md     (Template vazio com os tópicos do plano)
│   ├── 02_PRD.md              (Template vazio com Personas e User Stories)
│   ├── 03_SPECS.md            (Template vazio com Arquitetura e APIs)
│   └── 04_THREAT_MODEL.md     (Template vazio de Segurança)
├── src/                       (Onde o código vai nascer)
└── tests/                     (Onde os testes vão morar)
```

Crie um arquivo `CHECKLIST_INICIAL.md` na raiz com este passo a passo:

- [ ] 1. Copiar este template para a nova pasta do projeto.
- [ ] 2. Abrir no Antigravity.
- [ ] 3. Rodar `git init`.
- [ ] 4. Preencher `docs/01_PROJECT_PLAN.md` (Usar IA: Product Manager).
- [ ] 5. Preencher `docs/02_PRD.md` (Usar IA: Product Owner).
- [ ] 6. Preencher `docs/03_SPECS.md` (Usar IA: Nossos Prompts de Escalabilidade/Segurança).
- [ ] 7. Configurar ambiente local (Docker/Dependências).
- [ ] 8. Iniciar o desenvolvimento da primeira rota/funcionalidade.

---

### 💡 Resumo
Profissionais não começam abrindo o arquivo `index.js` ou `main.py`. Eles começam na pasta `/docs`. Quando você escreve o PRD e a SPEC primeiro, a Inteligência Artificial tem 100% de contexto do que você quer, eliminando alucinações e refatorações futuras.