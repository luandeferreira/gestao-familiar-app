# TAREFAS – Divisão de Trabalho

## Visão Geral da Equipe

Este documento sugere uma divisão de trabalho para uma equipe de **7 pessoas** responsável pelo desenvolvimento do **Gestão Familiar App**, baseada nos requisitos levantados.

A equipe é composta pelos seguintes perfis:

| # | Perfil                        | Responsabilidade Principal                          |
|---|-------------------------------|-----------------------------------------------------|
| 1 | Tech Lead / Arquiteto          | Arquitetura, decisões técnicas e revisão de código  |
| 2 | Dev Backend (Pleno)            | APIs, regras de negócio e banco de dados            |
| 3 | Dev Backend (Júnior)           | Integrações, serviços auxiliares e testes           |
| 4 | Dev Frontend / Mobile (Pleno)  | Telas principais, navegação e estado global         |
| 5 | Dev Frontend / Mobile (Júnior) | Componentes de UI, telas secundárias e acessibilidade |
| 6 | QA / Analista de Testes        | Plano de testes, automação e validação de critérios |
| 7 | UX Designer / PO               | Protótipos, pesquisa com usuários e backlog         |

---

## Sprint 0 – Planejamento e Configuração (1 semana)

| Tarefa | Responsável | Requisito Relacionado |
|--------|-------------|----------------------|
| Definir arquitetura da solução (mobile-first, offline-first) | Tech Lead | RNF4 |
| Configurar repositório, CI/CD e ambientes (dev, staging, prod) | Tech Lead | — |
| Criar protótipos de baixa fidelidade das telas principais | UX Designer / PO | HU01 a HU05 |
| Pesquisa com usuários periféricos para validar fluxos | UX Designer / PO | Objetivo Geral |
| Definir stack tecnológica e banco de dados local (SQLite/Hive) | Tech Lead + Dev Backend Pleno | RNF4 |
| Criar e priorizar backlog inicial no board de tarefas | UX Designer / PO | todos os RF |

---

## Sprint 1 – Fundação: Autenticação e Núcleo Familiar (2 semanas)

| Tarefa | Responsável | Requisito Relacionado |
|--------|-------------|----------------------|
| Implementar cadastro e autenticação de usuário (email + senha) | Dev Backend Pleno | RF1 |
| Implementar modelo de dados do núcleo familiar | Dev Backend Pleno | RF1, RN02 |
| Criar telas de cadastro e login | Dev Frontend Pleno | RF1 |
| Criar tela de gerenciamento de membros familiares | Dev Frontend Júnior | RF1, RN07 |
| Validar regra de limite de 10 membros | Dev Backend Júnior | RN07 |
| Escrever testes unitários para cadastro de membros | QA | RF1 |
| Garantir conformidade com LGPD (criptografia de dados pessoais) | Dev Backend Pleno + Tech Lead | RNF2, RN08 |

---

## Sprint 2 – Controle Financeiro: Receitas e Despesas (2 semanas)

| Tarefa | Responsável | Requisito Relacionado |
|--------|-------------|----------------------|
| Implementar modelo de dados de lançamentos financeiros | Dev Backend Pleno | RF2 |
| Criar API/serviço de registro de receitas e despesas | Dev Backend Pleno | RF2 |
| Implementar lógica de saldo em tempo real | Dev Backend Júnior | RF2, RN11 |
| Implementar alerta de saldo negativo | Dev Backend Júnior | RF2, RN11 |
| Criar tela de lançamentos (listagem, filtro por mês/categoria) | Dev Frontend Pleno | RF2 |
| Criar formulário de nova receita/despesa | Dev Frontend Júnior | RF2 |
| Implementar persistência offline com sincronização | Dev Backend Pleno + Dev Frontend Pleno | RNF4, RN06 |
| Escrever testes de integração para lançamentos financeiros | QA | RF2 |
| Validar usabilidade das telas com usuários reais | UX Designer / PO | HU01 |

---

## Sprint 3 – Benefícios Sociais e Alertas (2 semanas)

| Tarefa | Responsável | Requisito Relacionado |
|--------|-------------|----------------------|
| Implementar modelo de dados de benefícios sociais | Dev Backend Pleno | RF3 |
| Criar lógica de alerta por proximidade ao teto de renda | Dev Backend Pleno | RF3, RN04 |
| Implementar calendário de recebimentos de benefícios | Dev Backend Júnior | RF3 |
| Criar tela de cadastro e acompanhamento de benefícios | Dev Frontend Pleno | RF3 |
| Criar componente de calendário de recebimentos | Dev Frontend Júnior | RF3 |
| Implementar sistema de alertas/notificações locais | Dev Backend Júnior + Dev Frontend Pleno | RF7, RN10 |
| Criar tela de configuração de alertas de vencimento | Dev Frontend Júnior | RF7 |
| Escrever testes de validação de alertas e notificações | QA | RF3, RF7 |

---

## Sprint 4 – Metas Financeiras e Tarefas Domésticas (2 semanas)

| Tarefa | Responsável | Requisito Relacionado |
|--------|-------------|----------------------|
| Implementar modelo de dados de metas financeiras | Dev Backend Pleno | RF4 |
| Criar lógica de cálculo de esforço mensal e viabilidade | Dev Backend Pleno | RF4, RN14 |
| Criar tela de metas com barra de progresso | Dev Frontend Pleno | RF4 |
| Implementar modelo de dados de tarefas domésticas | Dev Backend Júnior | RF5 |
| Criar API/serviço de tarefas com frequências e responsáveis | Dev Backend Júnior | RF5 |
| Criar painel de tarefas familiares com filtros de status | Dev Frontend Júnior | RF5 |
| Escrever testes de cálculo de metas e regras de tarefas | QA | RF4, RF5 |
| Revisar protótipos e realizar testes de usabilidade | UX Designer / PO | HU03, HU04 |

---

## Sprint 5 – Relatórios e Acessibilidade (2 semanas)

| Tarefa | Responsável | Requisito Relacionado |
|--------|-------------|----------------------|
| Implementar serviço de geração de relatório mensal | Dev Backend Pleno | RF6 |
| Criar lógica de exportação em PDF | Dev Backend Júnior | RF6, RN12 |
| Criar tela de relatório com gráficos simplificados | Dev Frontend Pleno | RF6 |
| Aplicar diretrizes de acessibilidade WCAG 2.1 AA em todas as telas | Dev Frontend Júnior | RNF3 |
| Testar compatibilidade com leitores de tela (TalkBack/VoiceOver) | QA + Dev Frontend Júnior | RNF3 |
| Otimizar carregamento para conexões 2G | Dev Frontend Pleno + Tech Lead | RNF1 |
| Escrever testes de geração e exportação de relatórios | QA | RF6 |

---

## Sprint 6 – Testes, Correções e Lançamento (2 semanas)

| Tarefa | Responsável | Requisito Relacionado |
|--------|-------------|----------------------|
| Realizar testes de regressão completos | QA | todos os RF |
| Executar testes de carga e desempenho (metas RNF1) | QA + Tech Lead | RNF1 |
| Auditar segurança e conformidade LGPD | Tech Lead + Dev Backend Pleno | RNF2 |
| Corrigir bugs identificados nos testes | Dev Backend + Dev Frontend | — |
| Preparar documentação técnica e de usuário | Tech Lead + UX Designer / PO | — |
| Configurar loja de aplicativos (Google Play / App Store) | Tech Lead + UX Designer / PO | — |
| Realizar validação final com grupo de usuários periféricos | UX Designer / PO | Objetivo Geral |
| Lançamento da versão 1.0 (MVP) | toda a equipe | — |

---

## Resumo de Esforço por Perfil

| Perfil                        | Sprints de Maior Atuação         | Foco Principal                          |
|-------------------------------|----------------------------------|-----------------------------------------|
| Tech Lead / Arquiteto          | Sprint 0, 5, 6                   | Arquitetura, segurança e qualidade      |
| Dev Backend Pleno              | Sprint 1, 2, 3, 4, 5             | Regras de negócio e APIs                |
| Dev Backend Júnior             | Sprint 1, 2, 3, 4, 5             | Serviços auxiliares e sincronização     |
| Dev Frontend / Mobile Pleno    | Sprint 1, 2, 3, 4, 5             | Telas complexas e estado global         |
| Dev Frontend / Mobile Júnior   | Sprint 1, 2, 3, 4, 5             | Componentes UI e acessibilidade         |
| QA / Analista de Testes        | Sprint 1 ao 6                    | Testes unitários, integração e regressão |
| UX Designer / PO               | Sprint 0, 2, 4, 6                | UX, pesquisa com usuários e backlog     |
