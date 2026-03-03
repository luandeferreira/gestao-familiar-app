# Requisitos Funcionais e Não Funcionais

## Legenda

| Campo         | Descrição                                                      |
|---------------|----------------------------------------------------------------|
| ID            | Identificador único do requisito (RF = Funcional, RNF = Não Funcional) |
| Prioridade    | Alta / Média / Baixa                                           |
| Classificação | Funcional ou Não Funcional                                     |

---

## RF1 – Cadastro de Núcleo Familiar

| Campo         | Valor         |
|---------------|---------------|
| **ID**        | RF1           |
| **Prioridade**| Alta          |
| **Classificação** | Funcional |

**Descrição:** O sistema deve permitir que um usuário cadastre seu núcleo familiar, informando nome, data de nascimento, parentesco e renda individual de cada membro.

**Critérios de Aceitação (Gherkin):**

```gherkin
Funcionalidade: Cadastro de Núcleo Familiar

  Cenário: Cadastrar um novo membro na família
    Dado que o usuário está autenticado no sistema
    Quando ele acessa a seção "Minha Família" e clica em "Adicionar Membro"
    E preenche nome, data de nascimento e parentesco
    Então o novo membro deve aparecer na lista do núcleo familiar
    E o sistema deve exibir a mensagem "Membro adicionado com sucesso"

  Cenário: Tentar adicionar mais de 10 membros
    Dado que o núcleo familiar já possui 10 membros cadastrados
    Quando o usuário tenta adicionar um novo membro
    Então o sistema deve exibir a mensagem "Limite de membros atingido"
    E o botão "Adicionar Membro" deve ser desabilitado
```

---

## RF2 – Registro de Receitas e Despesas

| Campo         | Valor         |
|---------------|---------------|
| **ID**        | RF2           |
| **Prioridade**| Alta          |
| **Classificação** | Funcional |

**Descrição:** O sistema deve permitir o registro de receitas e despesas com data, valor, categoria e descrição, atualizando o saldo familiar em tempo real.

**Critérios de Aceitação (Gherkin):**

```gherkin
Funcionalidade: Registro de Receitas e Despesas

  Cenário: Registrar uma nova despesa
    Dado que o usuário está na tela de lançamentos
    Quando ele seleciona "Nova Despesa" e preenche valor, categoria e data
    E clica em "Salvar"
    Então o lançamento deve aparecer na lista de despesas do mês
    E o saldo disponível deve ser atualizado automaticamente

  Cenário: Registrar despesa que gera saldo negativo
    Dado que o saldo do mês é R$ 50,00
    Quando o usuário registra uma despesa de R$ 100,00
    Então o sistema deve exibir um alerta "Atenção: essa despesa deixará seu saldo negativo"
    E solicitar confirmação antes de salvar o lançamento

  Cenário: Registrar receita offline
    Dado que o usuário está sem conexão à internet
    Quando ele registra uma nova receita
    Então o lançamento deve ser salvo localmente
    E sincronizado automaticamente quando a conexão for restabelecida
```

---

## RF3 – Cadastro e Acompanhamento de Benefícios Sociais

| Campo         | Valor         |
|---------------|---------------|
| **ID**        | RF3           |
| **Prioridade**| Alta          |
| **Classificação** | Funcional |

**Descrição:** O sistema deve permitir o cadastro de benefícios sociais recebidos pela família, com alertas de datas e verificação de elegibilidade.

**Critérios de Aceitação (Gherkin):**

```gherkin
Funcionalidade: Cadastro de Benefícios Sociais

  Cenário: Cadastrar um benefício social
    Dado que o usuário está na seção "Benefícios"
    Quando ele adiciona um benefício informando nome, valor e data de recebimento
    Então o benefício deve ser exibido no calendário de recebimentos
    E contabilizado separadamente na seção de receitas

  Cenário: Alerta de proximidade do teto de renda
    Dado que o usuário recebe Bolsa Família com teto de renda cadastrado
    Quando a renda familiar registrada atingir 90% do limite permitido
    Então o sistema deve exibir um alerta "Atenção: sua renda está próxima do limite do benefício"
```

---

## RF4 – Planejamento de Metas Financeiras

| Campo         | Valor         |
|---------------|---------------|
| **ID**        | RF4           |
| **Prioridade**| Média         |
| **Classificação** | Funcional |

**Descrição:** O sistema deve permitir criar metas financeiras com valor e prazo, calculando automaticamente o esforço mensal necessário e acompanhando o progresso.

**Critérios de Aceitação (Gherkin):**

```gherkin
Funcionalidade: Planejamento de Metas Financeiras

  Cenário: Criar uma meta financeira atingível
    Dado que o usuário tem renda disponível de R$ 200,00/mês
    Quando ele cria uma meta de R$ 600,00 para daqui a 3 meses
    Então o sistema deve exibir "Você precisará guardar R$ 200,00 por mês"
    E criar uma barra de progresso iniciando em 0%

  Cenário: Criar uma meta inatingível
    Dado que o usuário tem renda disponível de R$ 100,00/mês
    Quando ele cria uma meta de R$ 600,00 para daqui a 2 meses
    Então o sistema deve alertar "Com sua renda atual, essa meta não é atingível no prazo"
    E sugerir um prazo alternativo viável

  Cenário: Registrar contribuição para a meta
    Dado que existe uma meta ativa
    Quando o usuário registra um depósito na meta
    Então o progresso deve ser atualizado visualmente
    E o sistema deve notificar quando a meta for concluída
```

---

## RF5 – Gestão de Tarefas Domésticas

| Campo         | Valor         |
|---------------|---------------|
| **ID**        | RF5           |
| **Prioridade**| Média         |
| **Classificação** | Funcional |

**Descrição:** O sistema deve permitir criar, atribuir e acompanhar tarefas domésticas entre os membros da família.

**Critérios de Aceitação (Gherkin):**

```gherkin
Funcionalidade: Gestão de Tarefas Domésticas

  Cenário: Criar e atribuir uma tarefa
    Dado que o usuário está na seção "Tarefas"
    Quando ele cria uma tarefa com nome, responsável e frequência semanal
    Então a tarefa deve aparecer no painel do responsável atribuído
    E o responsável deve receber uma notificação

  Cenário: Concluir uma tarefa
    Dado que existe uma tarefa pendente atribuída ao usuário
    Quando ele marca a tarefa como concluída
    Então o status deve mudar para "Concluída"
    E o painel familiar deve refletir a atualização em tempo real
```

---

## RF6 – Geração de Relatório Financeiro

| Campo         | Valor         |
|---------------|---------------|
| **ID**        | RF6           |
| **Prioridade**| Média         |
| **Classificação** | Funcional |

**Descrição:** O sistema deve gerar relatórios mensais com resumo de receitas, despesas e saldo, em linguagem acessível e com gráficos simplificados.

**Critérios de Aceitação (Gherkin):**

```gherkin
Funcionalidade: Relatório Financeiro

  Cenário: Visualizar relatório do mês
    Dado que existem lançamentos registrados no mês atual
    Quando o usuário acessa "Relatório do Mês"
    Então o sistema deve exibir total de receitas, total de despesas e saldo
    E apresentar um gráfico com as categorias de maior gasto

  Cenário: Exportar relatório em PDF
    Dado que o usuário está visualizando o relatório mensal
    Quando ele clica em "Exportar PDF"
    Então o sistema deve gerar um arquivo PDF do relatório
    E disponibilizá-lo para download ou compartilhamento
```

---

## RF7 – Alertas de Vencimento de Contas

| Campo         | Valor         |
|---------------|---------------|
| **ID**        | RF7           |
| **Prioridade**| Alta          |
| **Classificação** | Funcional |

**Descrição:** O sistema deve emitir alertas automáticos com antecedência mínima de 3 dias úteis antes do vencimento de contas recorrentes cadastradas.

**Critérios de Aceitação (Gherkin):**

```gherkin
Funcionalidade: Alertas de Vencimento

  Cenário: Alerta de conta próxima do vencimento
    Dado que existe uma conta recorrente com vencimento em 3 dias úteis
    Quando o sistema verificar as contas pendentes
    Então deve enviar uma notificação "Sua conta de luz vence em 3 dias"

  Cenário: Configurar prazo de alerta
    Dado que o usuário deseja ser avisado com 5 dias de antecedência
    Quando ele acessa as configurações de alertas e altera o prazo
    Então os alertas futuros devem respeitar o novo prazo configurado
```

---

## RNF1 – Desempenho em Conexões Lentas

| Campo         | Valor             |
|---------------|-------------------|
| **ID**        | RNF1              |
| **Prioridade**| Alta              |
| **Classificação** | Não Funcional |

**Descrição:** O sistema deve carregar as telas principais em até 3 segundos em conexões de 2G (velocidade mínima de 128 kbps), garantindo usabilidade para usuários com acesso limitado à internet.

---

## RNF2 – Segurança e Conformidade com a LGPD

| Campo         | Valor             |
|---------------|-------------------|
| **ID**        | RNF2              |
| **Prioridade**| Alta              |
| **Classificação** | Não Funcional |

**Descrição:** Todos os dados pessoais e financeiros devem ser armazenados com criptografia AES-256. O sistema deve disponibilizar funcionalidade de exclusão total de conta e dados, conforme exigido pela LGPD.

---

## RNF3 – Acessibilidade

| Campo         | Valor             |
|---------------|-------------------|
| **ID**        | RNF3              |
| **Prioridade**| Média             |
| **Classificação** | Não Funcional |

**Descrição:** O sistema deve ser compatível com leitores de tela (WCAG 2.1 nível AA), ter contraste de cores adequado e suportar fontes em tamanho ajustável para atender usuários com deficiência visual.

---

## RNF4 – Disponibilidade Offline

| Campo         | Valor             |
|---------------|-------------------|
| **ID**        | RNF4              |
| **Prioridade**| Alta              |
| **Classificação** | Não Funcional |

**Descrição:** As funcionalidades de registro de receitas, despesas e tarefas devem estar disponíveis sem conexão à internet, com sincronização automática ao reconectar.
