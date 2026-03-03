# Regras de Negócio

## Premissas

1. **RN01 – Acesso gratuito às funcionalidades essenciais**
   O sistema deve ser gratuito para funcionalidades básicas de controle financeiro e organização familiar. Funcionalidades avançadas, como relatórios detalhados ou backup em nuvem, poderão ser oferecidas como opcional premium.

2. **RN02 – Perfil familiar único por conta**
   Cada conta de usuário representa um núcleo familiar. O responsável principal pelo cadastro pode convidar outros membros adultos da família para acessar o sistema com perfis diferenciados.

3. **RN03 – Categorização de renda**
   Toda receita registrada deve ser classificada em uma das categorias: *Salário/Trabalho Formal*, *Trabalho Informal*, *Benefício Social* ou *Outra Renda*. Isso permite análises mais precisas do perfil econômico familiar.

4. **RN04 – Teto de renda para benefícios**
   O sistema deve alertar a família quando a renda registrada se aproximar do limite de corte para programas de benefício social cadastrados (ex.: Bolsa Família), evitando perda inadvertida do benefício.

5. **RN05 – Registro de benefícios sociais**
   Todos os benefícios sociais recebidos pela família devem ser registrados separadamente da renda por trabalho, para que o sistema possa calcular a dependência financeira de programas sociais e sugerir ações de autonomia financeira progressiva.

6. **RN06 – Modo offline obrigatório**
   As funcionalidades de registro de receitas, despesas e tarefas domésticas devem funcionar sem conexão à internet, sincronizando os dados quando a conexão for restabelecida.

## Restrições

7. **RN07 – Limite de membros por núcleo familiar**
   Um núcleo familiar pode ter no máximo 10 membros cadastrados, refletindo a realidade de famílias extensas em contextos periféricos.

8. **RN08 – Proteção de dados sensíveis**
   Dados financeiros, informações de benefícios sociais e dados pessoais dos membros familiares devem ser armazenados de forma criptografada, em conformidade com a Lei Geral de Proteção de Dados (LGPD).

9. **RN09 – Sem integração automática com bancos**
   O sistema não deve realizar integrações automáticas com contas bancárias ou carteiras digitais sem consentimento explícito do usuário, dada a sensibilidade do perfil socioeconômico do público-alvo.

10. **RN10 – Alertas de vencimento de contas**
    O sistema deve emitir alertas com antecedência mínima de 3 dias úteis antes do vencimento de contas recorrentes cadastradas (água, luz, aluguel, etc.), podendo esse prazo ser configurado pelo usuário.

11. **RN11 – Impedimento de saldo negativo não autorizado**
    O sistema deve alertar o usuário quando um lançamento de despesa provocar saldo negativo no orçamento do mês, exigindo confirmação explícita para que o registro seja salvo.

12. **RN12 – Histórico mínimo de 12 meses**
    O sistema deve manter o histórico financeiro dos últimos 12 meses disponível para consulta gratuita. Históricos mais antigos poderão ser exportados em formato PDF ou CSV.

13. **RN13 – Linguagem acessível**
    Todos os textos, mensagens de erro e relatórios do sistema devem ser redigidos em linguagem simples (nível de leitura do Ensino Fundamental), evitando jargões financeiros sem explicação.

14. **RN14 – Planejamento de metas realistas**
    Ao criar uma meta financeira, o sistema deve calcular automaticamente o valor mensal necessário com base na renda disponível registrada e alertar o usuário caso a meta seja inatingível no prazo definido.

15. **RN15 – Auditoria de alterações**
    Qualquer edição ou exclusão de lançamento financeiro deve ser registrada em log interno, garantindo rastreabilidade e evitando perdas acidentais de dados.
