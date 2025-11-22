🧪 Plano de Testes - Calculadora de Renda Fixa

Projeto: Calculadora de Investimentos de Renda Fixa
Disciplina: Gestão e Qualidade de Software (GQS)
Data: Novembro/2025

1. Escopo e Estratégia

1.1 Objetivo
Garantir a confiabilidade matemática e a usabilidade da calculadora, validando tanto a lógica de negócio financeira (cálculo de juros e impostos) quanto a validação de entrada de dados pelo usuário.

1.2 Estratégia de Teste

Adotamos uma abordagem híbrida com foco principal em Testes de Caixa Branca (White-Box), dado o acesso ao código-fonte.

Nível de Teste: Unitário e Integração de Componentes.
Ferramenta: [Vitest](https://vitest.dev/) com `@nuxt/test-utils`.

Técnicas Aplicadas:
    Análise de Valor Limite: Para validar as fronteiras das tabelas regressivas de IR e IOF.
    Particionamento de Equivalência: Para validar classes de dados válidos e inválidos nos inputs.

---

2. Casos de Teste Automatizados

Abaixo estão listados os cenários cobertos pela suíte de testes automatizados (`.spec.ts`).

2.1 Lógica de Negócio (Financeiro)
Foco: Garantir a precisão matemática dos investimentos.*

| ID   | Funcionalidade       | Técnica         | Cenário de Teste                                          | Resultado Esperado                                       |
| :--- | :---                 | :---            | :---                                                      | :---                                                     |
| CT01 | Tabela Regressiva IR | Particionamento | Investimento de 30 dias                                   | Alíquota de 22.5%                                        |
| CT02 | Tabela Regressiva IR | Valor Limite    | Investimento de 181 dias (Fronteira)                      | Alíquota cai para 20%                                    |
| CT03 | Tabela Regressiva IR | Valor Limite    | Investimento de 721 dias (Fronteira)                      | Alíquota mínima de 15%                                   |
| CT04 | Tabela de IOF        | Particionamento | Resgate em 10 dias                                        | Cobrança de 66% de IOF sobre o rendimento                |
| CT05 | Tabela de IOF        | Valor Limite    | Resgate em 30 dias (Fim da tabela)                        | Cobrança de 0% de IOF                                    |
| CT06 | Cálculo CDB          | Integração      | Simulação completa de CDB (1000 reais, 100% CDI, 10 dias) | Rendimento Bruto - IOF - IR = Líquido correto            |
| CT07 | Matemática Financeira| Unitário        | Função de Juros Compostos isolada                         | Cálculo exponencial preciso (sem erro de arredondamento) |

2.2 Interface e Validação (Componentes)
Foco: Garantir a robustez da entrada de dados e feedback ao usuário.

| ID   | Funcionalidade          | Técnica     | Cenário de Teste                   | Resultado Esperado |
| :--- | :---                    | :---        | :---                               | :--- |
| CT08 | Input de Valor          | Validação   | Usuário digita 0 (Zero)            | Exibir borda vermelha e erro "Obrigatório"             |
| CT09 | Input de Valor          | Validação   | Usuário digita -100 (Negativo)     | Exibir erro "Deve ser um número positivo"              |
| CT10 | Input de Valor          | Usabilidade | Renderização inicial do componente | Exibir prefixo "R$", ícone e label correto             |
| CT11 | Gerenciamento de Estado | Integração  | Usuário digita valor válido (1000) | Atualizar a Store (Pinia) e remover erros visuais      |
| CT12 | Acessibilidade          |  UI         | Verificação de labels HTML         | O atributo `for` do label corresponde ao `id` do input |


3. Ferramentas e Métricas

3.1 Execução
Para rodar a suíte de testes completa:

bash
pnpm test

3.2 Cobertura de Código (Coverage)

Utilizamos o provedor v8 para análise de cobertura. Para gerar o relatório:

Bash
npx vitest run --coverage
